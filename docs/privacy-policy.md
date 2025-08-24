
**Last Updated: 22.08.2025**

This privacy policy explains how the "Google DataTable Sync" Unreal Engine plugin ("the Plugin"), developed by OwlDev, handles your data when you authorize it to access your Google account.

**1. Data We Access**

When you grant permission, the Plugin accesses the following data via the Google Sheets API:

- The content of the specific Google Sheets you choose to sync with your Unreal Engine DataTables.
This access is necessary for the core functionality of the Plugin, which is to read data from and write data to your specified sheets.

**2. Data We Store**

The Plugin itself **DOES NOT** collect, transmit, or store any of your Google Sheets data on any external servers. All processing happens locally within the Unreal Editor on your machine.

To maintain your connection to Google services without requiring you to log in repeatedly, the Plugin securely stores an **OAuth 2.0 Refresh Token**. This token is stored locally on your computer within your Unreal Engine project's user settings file (`Config/User/EditorPerProjectUserSettings.ini`). This token is sensitive and should not be shared. The developer of the Plugin (OwlDev) does not have access to this token.

**3. How We Use Data**

Your Google Sheets data is used solely for:

- Importing data from a Google Sheet into an Unreal Engine DataTable.
- Exporting data from an Unreal Engine DataTable to a Google Sheet.

**4. Data Sharing**

We do not share your Google data or personal information with any third parties. The Plugin only communicates directly with Google's APIs as initiated by you from the Unreal Editor.

**5. How to Revoke Access**

You can revoke the Plugin's access to your Google Account at any time by visiting the "Third-party apps with account access" section in your Google Account settings: [https://myaccount.google.com/permissions](https://myaccount.google.com/permissions)

**6. Contact Us**

If you have any questions about this privacy policy, please contact us at: **rogozhnikovowl@gmail.com**
