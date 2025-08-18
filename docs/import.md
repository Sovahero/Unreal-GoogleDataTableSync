# Import

## What Import does
- Reads data from the linked tab.
- Shows a summary of changes before applying:
  - Added rows
  - Removed rows
  - Modified fields (old → new)
- Applies changes only after confirmation.

---

<img width="355" height="130" alt="DataTableImport" src="https://github.com/user-attachments/assets/f4d44b23-e613-4737-a646-7484324f5731" />

Diff preview dialog:

<img width="1002" height="889" alt="UeConfirmGoogleSync" src="https://github.com/user-attachments/assets/85bef0c4-c106-4c8e-b01d-478ed2343632" />

Result inside Unreal:

<img width="1515" height="728" alt="UeExampleStructsAll" src="https://github.com/user-attachments/assets/504c2931-1734-4bbe-9626-30b7dded845f" />

## Saved JSON snapshot
On each import the plugin saves a JSON file to the Temp File Location (default `Project/Intermediate/GoogleDTSync/<DataTableName>.json`).

!!! tip "External diff"
    You can open that JSON in your favorite diff tool.  
    If you want these snapshots tracked in VCS, point the Temp File Location to a tracked folder.

## Troubleshooting
- If import fails, verify the tab name and mapping via `Configure`, and ensure the header was not edited.
- When the DataTable structure changes, do a quick `Export` to regenerate the header, then paste your data below it.
