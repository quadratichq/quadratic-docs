# Google Analytics

<figure><img src="../.gitbook/assets/CleanShot 2026-01-16 at 15.15.52@2x.png" alt=""><figcaption></figcaption></figure>

### How to find Property ID

To find your Google Analytics Property ID:

1. Sign in to your [Google Analytics account](https://analytics.google.com/).
2. Select the Admin gear icon located at the bottom left of the screen.
3. In the "Property" column, use the dropdown menu to select the property you want the ID for.
4. The Property ID is displayed next to the property name in the form of "UA-XXXXXXXX-X".

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
