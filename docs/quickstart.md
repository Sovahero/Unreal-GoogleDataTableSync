# Quick Start

This section walks you through a complete first sync.

## 1) Enable the plugin
Edit → Plugins → search for “Google DataTable Sync”, enable it.

![Enable plugin](./images/UePlugins.png)

## 2) Open a DataTable
Open any `DataTable` asset. On first launch only `Configure` is enabled:

![DataTable first launch](./images/DataTableFirstLaunch.png)

## 3) Sign in (one time)
Click `Configure`. If access is not set yet, you’ll see the Google OAuth configuration dialog:

![Google OAuth config](./images/UeGoogleAuthConfig.png)

Enter your team’s `Client ID` and `Client Secret` (recommended), or enable Demo for a quick try. 

!!! warning "Use your own Google access (recommended)"
    Demo mode has shared quota. For production use your own credentials.
    See [Google Authentication](https://sovahero.github.io/Unreal-GoogleDataTableSync/setup-google-oauth.md) for step‑by‑step creation.

After you press “Save and Continue”, your browser will open and, upon success, show:
![Authentication Successful](./images/AuthSuccessful.png)


## 4) Link the DataTable to a sheet tab
Open the exact target tab in your sheet and copy the browser URL (this ensures the correct `gid`):

![Copy the sheet URL from the target tab](./images/GoogleCopySheetUrl.png)

Paste it in the configuration dialog and type the tab name:

![Configure Google Sheet mapping](./images/UeGoogleSheetConfig.png)

Click `Save`. To verify the link, use `Open Sheet`:

![Open the associated sheet](./images/DataTableOpenSheet.png)

## 5) Do an initial Export
Click `Export`. This generates the header and uploads all rows.

![Export button](./images/DataTableExport.png)

You’ll see the export options dialog:

![Export options](./images/UeExportOptions.png)

After export, your Google Sheet will contain a structured, readable header.

## 6) Import changes
Make edits in the sheet (add rows, adjust values), then click `Import`:

![Import button](./images/DataTableImport.png)

Review the diff dialog and confirm:

![Confirm Google Sync](./images/UeConfirmGoogleSync2.png)

The DataTable updates in‑editor:

![Imported result in UE](./images/UeExampleStructsAll.png)