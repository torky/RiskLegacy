# Setup
 - The `RiskLegacy` project can go anywhere.  
 - The `RiskLegacyUI` project will need to go under `C:\Program Files (x86)\StarCraft II\Mods\`. 
 - There are two **VSCode** extensions, 
	 - Talv's **`StarCraft 2 Galaxy Script`** extension that will do syntax highlighting and stuff for `.galaxy` files.  Sometime's it highlights files saying that the method was already initialized elsewhere, but mainly can be ignored
	 - Talv's **`StarCraft 2 Layout`** extension that will do syntax highlighting for `.SC2Layout` files. This will be useful for the `RiskLegacyUI` project.
 - Use the **StarCraft II Editor** for testing.

# Architecture
## RiskLegacy Project
### General
- The general folder/file structure is the overarching functionality should be a folder. Any relating files should be inside that folder. 
- All scripts should be under the `scripts` folder, with the exception of the `MapScript.galaxy` and `MapScriptReference.galaxy` (the `MapScriptReference.galaxy` file can be moved).

### `MapScript.galaxy`
 - The `MapScript.galaxy` the `Main` file essentially.
 - The `//Level X` comment essentially means that it depends on at least one `include` that is at least one `Level` lower than it. 
 - The file containing any code must be included before you use it. I'm using the `MapScript.galaxy` file to clearly mark the order of certain file hierarchies so that it's easy to see.
 
### `MapScriptReference.Galaxy`
 - This file isn't used, but can be helpful to figure out things that were already figured out. It contains the old code compiled from the SC2 Editor.

### Naming Conventions
- Constants are `c_camelCase` except for ints that start with `total` because I wanted to keep things consistent.
- Methods are `PascalCase`.
- Triggers are  `gt_PascalCase`.
- Trigger initialization methods are `gt_PascalCase_Init`
- Files are `CameCase` 
- Folders are `camelCase`, but I have no idea because so far they are all one word. :)
- Parameters are `camelCase`.
- Local variables are `camelCase`.
- Structs are `PascalCase`.
- Struct variables are `camelCase`.
- Typedefs are `PascalCase`.
- Global variables are `camelCase`.

## RiskLegacyUI Project
### General
- Files are under the `Base.SC2Data/UI/RiskLegacy` Folder except for the `DescIndex.SC2Layout` file, which is in the `Base.SC2Data/UI/Layout` folder.

### `DescIndex.SC2Layout`
- Similar to the `MapScript.galaxy` file, we are using it to include the main hierarchies of files, and files must be included in the proper order otherwise SC2 will error.

### Naming Conventions
- Everything is `PascalCase`.
