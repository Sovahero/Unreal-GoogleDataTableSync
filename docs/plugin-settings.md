# Project Settings

Open: `Edit → Project Settings → Plugins → Google DataTable Sync`

![Project Settings](./images/UeProjectSettings.png)

## Common options
- **Sheet Mappings** — for each DataTable (by asset name), store the Google Sheet ID/URL, tab name, and `gid`.

- **Request Timeout** — increase for slow networks or large exports.

- **Temp File Location** — On each import the plugin saves a JSON file to the Temp File Location (default `Project/Intermediate/GoogleDTSync/<DataTableName>.json`).

!!! tip "External diff"
    You can open that JSON in your favorite diff tool.  
    If you want these snapshots tracked in VCS, point the Temp File Location to a tracked folder.

## Advanced (usually keep defaults)
- **Header Keywords** — markers placed in header rows to represent structure:
  - Value keyword (default `value'`)
  - Object keyword (default `struct'`)
  - Array keyword (default `arr'`)
  - Map keyword (default `map'`)

Changing these affects how headers are generated and parsed. You should only change these if they conflict with your own data column names.

## Personal (per‑user)
Saved outside version control:
- Refresh Token (created after first sign‑in)
- Last used Client ID (to auto‑invalidate tokens on change)
- Last export options (dialog state)