# Browser compatibility

Quadratic has **first-tier** browser support for:

* Google Chrome\*
* Chromium browsers (Arc, Edge, Opera, etc.)

_\*All of our developers and automated tests use Chrome, giving it first-class support status._

Non-Chromium browsers receive **second-tier** support and are less performant than first-tier browsers:

* Safari
* Firefox
* Mobile Browsers (read-only)

To file a browser-specific issue, please [contact us](https://quadratichq.com/contact).&#x20;

## Troubleshooting

<figure><img src="../.gitbook/assets/CleanShot 2024-07-24 at 10.05.27@2x.png" alt="" width="563"><figcaption></figcaption></figure>

### Hardware acceleration

If you receive this error message in Chrome, a possible cause is that your browser's hardware acceleration is turned off, preventing WebGL from working.&#x20;

**Solution:** You can enable hardware or graphics acceleration by visiting `chrome://settings/system` and toggling on hardware or graphics acceleration.&#x20;

<figure><img src="../.gitbook/assets/CleanShot 2024-07-24 at 10.08.43@2x.png" alt=""><figcaption><p>Toggle must be on for Quadratic to work in your browser</p></figcaption></figure>
