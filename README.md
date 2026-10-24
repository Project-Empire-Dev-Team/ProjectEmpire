# Project Empire

A 2-developer Unreal Engine 5 project. 

## Prerequisites & Setup

Before cloning or opening this project, you **MUST** complete the following steps to prevent repository corruption:

1. **Install Git LFS:** Ensure Git Large File Storage is installed on your machine.
   ```bash
   git lfs install
   ```
2. **Clone the Repo:** Clone this repository normally. Git LFS will automatically pull down the binary source assets.
3. **Engine Version:** This project is built using **Unreal Engine 5.8.2**. Ensure you have the exact version installed via the Epic Games Launcher.

## Git & Commit Rules

The repository .gitignore blocks all files by default, only allowing approved Unreal assets and other selected file types to prevent repository bloating.

* **Adding Raw Files:** By default, only `.uasset`, `.umap`, and specific code files are allowed in the `/Content` folder. If you are adding raw files (like `.fbx`, `.png`, or `.wav`), you **must** use the `/RawContent` folder where all file types are allowed and tracked via LFS.
* **Empty Folders:** Git does not track empty directories. If you create a folder, place a `.gitkeep` file inside it to push it to the remote repository.
* **Fix Up Redirectors:** Before pushing changes that involve moving or deleting assets, right-click the `Content` folder in UE5 and click **"Update Redirector References"**.

## Content Directory Layout

To maintain a clean project, please follow this basic folder hierarchy inside `ProjectEmpire/`:

```text
ProjectEmpire/
├── Content/
│   ├── ProjectEmpire/
│   │   ├── Framework/           # Architecture classes defining core game flow mechanics
│   │   │   ├── Coop/            # Dedicated multi-session tech and multiplayer logic overrides
│   │   │   └── Common/          # Base elements common to all gameplay contexts
│   │   ├── GameFeatures/        # Simulation systems and entity blueprints
│   │   │   ├── Coop/            # Dedicated multiplayer logic overrides
│   │   │   └── Common/          # Base simulation systems common to all gameplay contexts 
│   │   ├── Maps/                   
│   │   │   ├── Coop/            # Map stitching systems for multiplayer sessions
│   │   │   └── Common/          # Game maps
│   │   ├── MaterialLibrary/     # Parent master materials 
│   │   └── UI/                  # HUD widgets and application menus
│   │       ├── Coop/            # Networked multiplayer lobby menus and session widgets
│   │       └── Common/          # Core status layouts and reusable UI widgets
│   ├── Developers/              # Local individual sandboxes for isolated prototyping
│   │   ├── Isaac/
│   │   └── Quillan/
│   └── ExternalContent/         # Marketplace dependencies and vendor packages (e.g., Fab)
└── RawContent/                  # Staging folder for raw files 
```
