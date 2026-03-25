---
description: Embed Quadratic in other apps and websites.
---

# Embedding Quadratic spreadsheets

You can embed a Quadratic spreadsheet in your own website or app so visitors can view or interact with it without leaving the page. The spreadsheet runs in an iframe and supports the same features as opening the file in Quadratic (formulas, Python, JavaScript, charts, etc.), with options to restrict editing or show a single sheet.

### Prerequisites

To create an embed link, you need **edit access** to the file. The embed link itself controls access — once created, anyone with the embed link can view the file regardless of the file's sharing settings. This is similar to "share by link" — the embed UUID acts as a secret access token.

To revoke embed access, delete the embed link from the Share dialog. The file's publicLinkAccess setting ("Anyone with the link") does not affect embed access.

### Getting the embed link

1. Open the spreadsheet in Quadratic.
2. Go to **File → Share** (or use the Share option in the top bar).
3. Scroll to the **Embed** section at the bottom and expand it.
4. Optionally adjust the embed options (read-only, sheet, preload—see below).
5. Copy the embed URL from the read-only box, or use **Copy link** to copy the URL and **Copy HTML** to copy a ready-made `<iframe>` snippet.

The base embed URL looks like:

```
https://app.quadratichq.com/embed?embedId=YOUR_EMBED_UUID
```

The `embedId` is a unique identifier for the embed link, separate from the file's UUID. This ensures the file's UUID is never exposed in the embed URL.

### Embed URL parameters

You can add query parameters to control how the embed behaves.

| Parameter          | Description                                                                                                                                                     |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `embedId`          | **Required** for embedding an existing file. The embed link's UUID (from the Share dialog). Omit when using `import`, `uploadMode`, or for a blank spreadsheet. |
| `import`           | URL of a file to import (CSV, Excel, Parquet, or Quadratic grid). The file is fetched and opened in the embed. See Embedding with imported files.               |
| `uploadMode`       | Set to `postMessage` to upload a file via postMessage. See Uploading files via postMessage.                                                                     |
| `readonly`         | If present, the embed loads in read-only mode. Viewers cannot edit cells or run code.                                                                           |
| `sheet`            | Name of a single sheet to display. When set, only that sheet is shown and the sheet bar is hidden. Omit to show all sheets.                                     |
| `preload`          | Comma-separated list of runtimes to preload for faster first run: `python`, `js`, or `python,js`.                                                               |
| `hideHeadings`     | If present, row and column headings (A, B, C… and 1, 2, 3…) are hidden.                                                                                         |
| `hideGridLines`    | If present, grid lines between cells are hidden.                                                                                                                |
| `noFormatting`     | If present, the formatting bar and cell position/goto input are hidden.                                                                                         |
| `noClampToContent` | If present, users can pan the viewport beyond the edges of sheet content. By default, panning is clamped to the content bounds.                                 |
| `noZoom`           | If present, zooming is disabled and zoom controls are hidden.                                                                                                   |

The `embedId`, `import`, and `uploadMode` parameters are mutually exclusive: use `embedId` to embed an existing Quadratic file, `import` with a URL to load a file from the web, `uploadMode` to upload a file via postMessage, or omit all three for a blank spreadsheet.

#### Examples

* View-only embed: `https://app.quadratichq.com/embed?embedId=abc-123&readonly`
* Single sheet, read-only: `https://app.quadratichq.com/embed?embedId=abc-123&readonly&sheet=Summary`
* Preload Python and JavaScript: `https://app.quadratichq.com/embed?embedId=abc-123&preload=python,js`
* Minimal UI (no headings, grid lines, or formatting bar): `https://app.quadratichq.com/embed?embedId=abc-123&hideHeadings&hideGridLines&noFormatting`
* Fixed zoom, clamped viewport: `https://app.quadratichq.com/embed?embedId=abc-123&noZoom`

### Embedding with imported files

You can embed Quadratic and have it load a spreadsheet from a URL instead of an existing Quadratic file. Use the `import` parameter with the full URL of the file. The file is fetched when the embed loads and opened in the viewer. The original file is never modified — if the user signs in to Quadratic, a duplicate is created in their account.

**Supported formats:**

* **CSV** (`.csv`)
* **Excel** (`.xlsx`, `.xls`)
* **Parquet** (`.parquet`)
* **Quadratic grid** (`.grid`)

The format is inferred from the URL path (the file extension). The URL must be publicly accessible so the embed can fetch it (same-origin or CORS permitting).

**Examples:**

* Import a CSV from your site: `https://app.quadratichq.com/embed?import=https://yoursite.com/data/sales.csv`
* Import an Excel file (read-only): `https://app.quadratichq.com/embed?import=https://yoursite.com/reports/q4.xlsx&readonly`

You can combine `import` with other embed parameters (`readonly`, `sheet`, `preload`, etc.) the same way as with `embedId`.

### Uploading files via postMessage

For larger files or files you don't want to host publicly, you can upload file data directly to the embed iframe using the browser's postMessage API. This is useful when the file is generated dynamically or stored locally.

Set `uploadMode=postMessage` in the embed URL:

```
https://app.quadratichq.com/embed?uploadMode=postMessage
```

Then, in your host page, listen for a `quadratic-embed-upload-ready` message from the iframe and respond by posting the file data:

```html
<iframe id="quadratic-embed" src="https://app.quadratichq.com/embed?uploadMode=postMessage" width="100%" height="600" style="border: none;"></iframe>
<script>
const iframe = document.getElementById('quadratic-embed');
const fileName = 'data.csv';
const fileData = new Uint8Array([/* your file bytes */]).buffer;

window.addEventListener('message', (event) => {
  if (event.source === iframe.contentWindow && event.data?.type === 'quadratic-embed-upload-ready') {
    iframe.contentWindow.postMessage({
      type: 'quadratic-embed-upload',
      uploadName: fileName,
      uploadData: fileData
    }, '*', [fileData]);
  }
});
</script>
```

The embed will import the file and display it. Supported formats are the same as for URL imports (CSV, Excel, Parquet, and Quadratic grid).

You can combine `uploadMode` with other embed parameters (`readonly`, `sheet`, `preload`, etc.) the same way as with `embedId`.

### Blank embed

Omit `embedId`, `import`, and `uploadMode` to load a blank spreadsheet:

```
https://app.quadratichq.com/embed
```

This creates an empty spreadsheet that users can interact with. All changes are local-only and lost when the page is refreshed.

### Adding the embed to your site

Use an iframe and set the `src` to your embed URL:

```html
<iframe
  src="https://app.quadratichq.com/embed?embedId=YOUR_EMBED_UUID"
  width="100%"
  height="600"
  style="border: none;">
</iframe>
```

Adjust `width` and `height` to fit your layout. The Share dialog's **Copy HTML** button gives you a snippet you can paste into your page.

### Embed settings page

You can configure embed options interactively using the embed settings page at:

```
https://app.quadratichq.com/embed/settings
```

This page lets you:

* Enter an embed ID, upload a file, or specify a file URL
* Configure size, appearance, and performance options
* Preview the embed in real-time
* Copy the generated iframe HTML code

### Embed options explained

* **Read-only** — When enabled, the embedded spreadsheet is view-only. No edits or code execution.
* **Only show sheet** — If you enter a sheet name, only that sheet is shown and the sheet tabs are hidden. Leave blank to show all sheets.
* **Preload Python** / **Preload JavaScript** — Preloads the corresponding runtime so the first run of Python or JavaScript in the embed is faster. Helpful if you know visitors will run code.
* **Hide headings** — When enabled, row and column headings (A, B, C… and 1, 2, 3…) are hidden for a cleaner look.
* **Hide grid lines** — When enabled, the grid lines between cells are hidden for a cleaner presentation.
* **Hide formatting bar** — When enabled, the formatting bar and cell position/goto input are hidden, even in non-read-only mode.
* **Allow panning beyond content** — By default, the viewport is clamped to the sheet content bounds. Enable this to let users pan beyond the edges.
* **Disable zooming** — When enabled, zooming is locked and zoom controls (menu, pinch, wheel) are hidden.

### Viewing and editing in the embed

Anyone with the embed link can open the spreadsheet. They can change cells and run code in the browser regardless of whether the file is shared as **Can view** or **Can edit**, but **no one can ever modify your original file through an embed**. All changes happen in a temporary, in-browser session.

If a viewer signs in to Quadratic (or opens the file from the embed), a **duplicate** of the file is created in their account. They work on their own independent copy from that point on — your original file is never touched. This means:

* Your data is always safe.
* Viewers get the full Quadratic experience (formulas, Python, JavaScript, charts, etc.).
* Saving requires a Quadratic account and always produces a separate copy.

### Edit in Quadratic button

The embed displays an "Edit in Quadratic" button that allows users to export the current state of the embedded spreadsheet (including any local changes) to their Quadratic account. Clicking this button:

1. Exports the current grid data
2. Uploads it to Quadratic
3. Opens a new tab where the user can sign in and claim the file

The claimed file is a copy — the original embedded file is never modified.
