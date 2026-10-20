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

The repository .gitignore blocks all files by default, only allowing approved Unreal asset and other selected file types to prevent repository bloating.

* **Adding New File Types:** By default, only `.uasset`, `.umap`, and specific code files are allowed. If you add raw files (like `.fbx`, `.png`, or `.wav`) to the `/Content` folder, you **must** update the `.gitignore` to allow them, and the `.gitattributes` to track them via LFS. Alternatively only add raw files to the `/RawContent` folder where all file types are allowed and tracked via LFS.
* **Empty Folders:** Git does not track empty directories. If you create a folder structure, place a `.gitkeep` file inside it to push it to the remote repository.
* **Fix Up Redirectors:** Before pushing changes that involve moving or deleting assets, right-click the `Content` folder in UE5 and click **"Update Redirector References"**.

## Content Directory Layout

To maintain a clean project, please follow this basic folder hierarchy inside `/Content/YourProjectName/`:

* `_Core/` — GameModes, PlayerControllers, GameInstances.
* `Art/` — Textures, Materials, Skeletal/Static Meshes.
* `Blueprints/` — All gameplay logic Blueprints.
* `Levels/` — Sub-levels and Persistent Maps.
* `UI/` — Widgets, HUDs, and fonts.
