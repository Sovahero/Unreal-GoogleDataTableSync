# Export

## What Export does
- Analyzes the DataTable structure (including nested structs, arrays, maps).
- Generates a structured header and clears the target tab.
- Uploads data in efficient chunks with progress.
- Optionally applies styling (header background, bold/italic keywords, borders, frozen rows/columns, auto/explicit widths).

!!! warning "Tab reset"
    The target tab is fully cleared during Export and rewritten (content, merges, formatting).

## Export Options
- Include empty arrays and maps — keep columns even if the collection is empty.
- Apply cell coloring and borders — improves readability.

![Export options](./images/UeExportOptions.png)

!!! tip "Good practice"
    - One DataTable → one sheet tab.
    - Keep formulas/notes on a separate tab (they'll be erased by Export).
    - If you change the DataTable structure, do a fresh Export to regenerate headers before editing in Sheets.

## Example (structs, arrays, maps)

Example row struct definition:

![Example struct layout](./images/UeExampleStruct2.png)

Example row values in UE:

![Example row values](./images/UeExampleStruct.png)

After Export, the Google Sheet gets a readable, hierarchical header. You can add new rows under the header and edit values:

![Export result in Google Sheets](./images/GoogleExampleStruct.png)
