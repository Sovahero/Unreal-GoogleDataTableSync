# Quick Start

This section walks you through a complete first sync.


## 1) Enable the plugin

Edit → Plugins → search for "Google DataTable Sync", enable it.

<img width="661" height="283" alt="UePlugins" src="https://github.com/user-attachments/assets/c9ec061b-8291-4919-af96-b54d36092704" />


## 2) Open a DataTable

Open any `DataTable` asset. On first launch only `Configure` is enabled:

<img width="511" height="91" alt="DataTableFirstLaunch" src="https://github.com/user-attachments/assets/f75a1d89-128b-41f1-8d8c-21f3821606bf" />


## 3) Sign in

Click `Configure`. If access is not set yet, you'll see the Google OAuth configuration dialog:

<img width="691" height="632" alt="UeGoogleAuthConfig" src="https://github.com/user-attachments/assets/73aecb36-d734-48f7-876e-b5885746bb1f" />

Enter your team's `Client ID` and `Client Secret` (recommended), or enable Demo for a quick try. 

!!! warning "Use your own Google access (recommended)"
    Demo mode has shared quota. For production use your own credentials.
    See [Google Authentication](setup-google-oauth.md) for step‑by‑step creation.

## 4) Link the DataTable to a sheet tab

Open the exact target tab in your sheet and copy the browser URL (this ensures the correct `gid`):

<img width="1120" height="490" alt="GoogleCopySheetUrl" src="https://github.com/user-attachments/assets/4bf67bf3-5364-4f7e-ae5a-0e8f649c2a78" />

!!! warning "Sheet Name"
    To avoid errors, use **Cyrillic** for the Sheet Name.

Paste it in the configuration dialog and type the tab name:

<img width="1121" height="366" alt="UeGoogleSheetConfig" src="https://github.com/user-attachments/assets/a979df10-1bd6-46ab-b759-c6d2346d7236" />

Click `Save`. To verify the link, use `Open Sheet`:

<img width="365" height="137" alt="DataTableOpenSheet" src="https://github.com/user-attachments/assets/7cc72cea-4d3e-4029-ac2f-6449c03803c7" />


## 5) Do an initial Export

Click `Export`. This generates the header and uploads all rows.

<img width="507" height="135" alt="DataTableExport" src="https://github.com/user-attachments/assets/66704462-6c39-4338-b96d-a851ba9871dd" />

You'll see the export options dialog:

<img width="723" height="307" alt="UeExportOptions" src="https://github.com/user-attachments/assets/2f6fa577-7af8-4b85-94c6-0c591607d98a" />

After you press "Export", your browser will open and, upon success, show:

<img width="1015" height="271" alt="AuthSuccessful" src="https://github.com/user-attachments/assets/14e4d17f-1390-4cce-bb27-62d803900bf2" />

After export, your Google Sheet will open and contain a structured, readable header.

<img width="2067" height="603" alt="GoogleExampleStruct" src="https://github.com/user-attachments/assets/4859cb9b-d22a-49ae-a0f3-d62b1af06772" />


## 6) Import changes

Make edits in the sheet (add rows, adjust values), then click `Import`:

<img width="355" height="130" alt="DataTableImport" src="https://github.com/user-attachments/assets/670bcb51-ca4a-446b-bcd2-0082fb1e7786" />

Review the diff dialog and confirm:

<img width="402" height="350" alt="UeConfirmGoogleSync2" src="https://github.com/user-attachments/assets/52a6e169-6fa0-4406-a6a3-d62e3c7100d0" />

The DataTable updates in‑editor:

<img width="1515" height="728" alt="UeExampleStructsAll" src="https://github.com/user-attachments/assets/5513b835-aa9b-4a70-8ba4-27c4669ed519" />
