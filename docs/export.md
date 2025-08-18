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

<img width="723" height="307" alt="UeExportOptions" src="https://github.com/user-attachments/assets/3498db7b-43c6-4464-a740-5eb04d54e7a6" />

!!! tip "Good practice"
    - One DataTable → one sheet tab.
    - Keep formulas/notes on a separate tab (they'll be erased by Export).
    - If you change the DataTable structure, do a fresh Export to regenerate headers before editing in Sheets.

## Example (structs, arrays, maps)

Example row struct definition:

<img width="528" height="342" alt="UeExampleStruct2" src="https://github.com/user-attachments/assets/ab1cf26f-412b-4fdb-ab2a-2028cf1b6fd0" />

Example row values in UE:

<img width="682" height="695" alt="UeExampleStruct" src="https://github.com/user-attachments/assets/93e6ca40-eb15-4bcc-a991-f5a82d61a094" />

After Export, the Google Sheet gets a readable, hierarchical header. You can add new rows under the header and edit values:

<img width="2067" height="603" alt="GoogleExampleStruct" src="https://github.com/user-attachments/assets/00906d34-7468-4fa6-ad25-b1bdaba05e9d" />
