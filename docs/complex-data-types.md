## How complex data types are handled

The plugin intelligently handles Unreal Engine's complex data types by preserving their internal structure and metadata. For certain field types, additional path information is included to maintain data integrity.

### Transform and Rotation Data

When working with `FTransform` or `FRotator` types, it's important to understand how the plugin handles rotation data:

**FTransform Rotation (Quaternions)**  
The plugin exports rotation from `FTransform` as a quaternion (X, Y, Z, W values), not as degrees. This is Unreal's internal representation of rotation.

- **In UE Editor**: You see rotation as Roll/Pitch/Yaw in degrees (e.g., 0°, 0°, 135°)
- **In Google Sheets**: You see the quaternion values (e.g., X≈0.0047, Y≈-0.0114, Z≈0.9238, W≈0.3827)
- **After Import**: UE converts the quaternion back to degrees, which may show slightly different values due to floating-point precision

!!! warning "Quaternion Requirements"
    Quaternions must be **unit quaternions** (length = 1). Arbitrary values like "111" will be normalized by the engine and produce unexpected rotation angles.

**Common Quaternion Values:**
- **No rotation**: `X=0, Y=0, Z=0, W=1`
- **90° Yaw**: `X=0, Y=0, Z=0.70710678, W=0.70710678`
- **90° Pitch**: `X=0, Y=0.70710678, Z=0, W=0.70710678`
- **90° Roll**: `X=0.70710678, Y=0, Z=0, W=0.70710678`

**FRotator (Direct Degrees)**  
If you use `FRotator` instead of `FTransform`, the plugin exports rotation as Pitch/Yaw/Roll in degrees, making it much more intuitive to edit in Google Sheets.

!!! tip "Recommended approach for manual editing"
    For DataTables that require frequent manual rotation editing, consider splitting `FTransform` into separate fields:
    
    - `FVector Location`
    - `FRotator Rotation` (exported as degrees)
    - `FVector Scale`
    
    Then combine them into `FTransform` in your code/Blueprint. This keeps the Google Sheets data human-readable.

### Asset References
When your DataTable contains references to assets (textures, meshes, blueprints, etc.), the plugin exports the full asset path along with the reference data. This ensures that when you import the data back, Unreal Engine can correctly resolve and link to the original assets.

### Localized Text (NSLOCTEXT)
The plugin preserves Unreal's localization format completely. In Google Sheets you'll see the full `NSLOCTEXT("Package","Key","Source")` structure, which includes:

- **Package**: The localization namespace
- **Key**: The unique identifier for this text entry  
- **Source**: The actual display text

- In UE:

  <img width="707" height="177" alt="UeExampleText" src="https://github.com/user-attachments/assets/e5937901-a201-4ff6-9a2f-2598d580b3d0" />

- In Sheets:  
  
  <img width="872" height="281" alt="GoogleExampleText" src="https://github.com/user-attachments/assets/4e4f79bb-4891-4183-b81c-c076df086290" />

!!! tip "Editing localized text"
    To change the visible text, edit only the last `"Source"` parameter.  
    Do not change `Package` and `Key` unless you know your localization pipeline.

### Other Complex Types
Similar data preservation applies to:
- **Soft Object References**: Full asset paths with package information
- **Class References**: Blueprint class paths and metadata
- **Curve References**: Data table and curve asset paths
- **Material Parameter Collections**: Parameter names and collection paths

This approach ensures that no critical linking information is lost during the export/import process, maintaining the integrity of your game data.
