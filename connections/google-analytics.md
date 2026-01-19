# Google Analytics

<figure><img src="../.gitbook/assets/CleanShot 2026-01-16 at 15.15.52@2x.png" alt=""><figcaption></figcaption></figure>

### How to find Property ID

To find your Google Analytics Property ID:

1. Sign in to your [Google Analytics account](https://analytics.google.com/).
2. Select the Admin gear icon located at the bottom left of the screen.
3. In the "Property settings" section, select "Property details".
4. The Property ID is displayed on the top right of the screen. It is a purely numeric identifier for the entire property container (e.g., `123456789`).

### How to find service account JSON

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. Create a new project or select an existing project.
3. Navigate to the "IAM & Admin" section and select "Service Accounts."
4. Click "Create Service Account."
5. Enter a Service Account name and description, then click "Create."
6. Assign roles as needed, such as "Viewer" for read-only access.
7. Click "Done" after configuring roles.
8. In the "Actions" column for your service account, click the three-dot menu and select "Manage keys."
9. Click "Add Key," choose "JSON," and click "Create."
10. Download the JSON file to your computer. This file contains the credentials for your service account.

### How to enable API access

1. Open [Google Cloud Console](https://console.cloud.google.com/) and select the GCP project that owns your service account.
2. Go to APIs & Services → Library.
3. Search for "Google Analytics Data API" and click Enable.
4. (Recommended) Also enable "Google Analytics Admin API" for metadata access.
5. Confirm both APIs appear under APIs & Services → Enabled APIs for the same project.

### How to grant the Service Account access in GA4

1. Copy the client\_email value from your service account JSON (ends with .iam.gserviceaccount.com).
2. Open [Google Analytics](https://analytics.google.com/) and navigate to Admin for the correct GA4 property.
3. Select Property access management.
4. Click "Add users" and paste the service account email.
5. Assign the Editor role (recommended for setup; you can downgrade to Viewer later).
6. Save changes.
