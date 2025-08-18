# Import

## What Import does
- Reads data from the linked tab.
- Shows a summary of changes before applying:
  - Added rows
  - Removed rows
  - Modified fields (old → new)
- Applies changes only after confirmation.

![Import button](./images/DataTableImport.png)

Diff preview dialog:

![Confirm Google Sync](./images/UeConfirmGoogleSync2.png)

Result inside Unreal:

![Result after import](./images/UeExampleStructsAll.png)

## Saved JSON snapshot
On each import the plugin saves a JSON file to the Temp File Location (default `Project/Intermediate/GoogleDTSync/<DataTableName>.json`).

!!! note "External diff"
    You can open that JSON in your favorite diff tool.  
    If you want these snapshots tracked in VCS, point the Temp File Location to a tracked folder.

## Troubleshooting
- If import fails, verify the tab name and mapping via `Configure`, and ensure the header was not edited.
- When the DataTable structure changes, do a quick `Export` to regenerate the header, then paste your data below it.