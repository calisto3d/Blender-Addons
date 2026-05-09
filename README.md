# UEFN Exporter

A Blender add-on for preparing assets for UEFN / Unreal Engine.

## Features

- Rename selected meshes with an Unreal-friendly `SM_` prefix.
- Fix pivots to bottom-center and move objects to world origin.
- Bake texture maps with Cycles.
- Optionally create a new `_Baked` mesh with the baked material applied.
- The baked mesh keeps only the baked/export UV map, so FBX importers do not pick the wrong UV channel.
- Export each selected mesh into its own `SM_<AssetName>` folder.
- Mesh export is mesh-only. Textures are not copied during export because baked textures are already saved by the bake step.

## Install

1. In Blender, go to **Edit > Preferences > Add-ons**.
2. Click **Install...**.
3. Select the add-on zip file.
4. Enable **UEFN Exporter**.
5. Open the 3D View sidebar with **N** and use the **UEFN Exporter** tab.

## Recommended workflow

1. Select the original mesh.
2. Set the **Destination Folder**.
3. In **Bake Textures**, choose the maps, resolution, samples, and UV mode.
4. Enable **Create Mesh with Baked Material**.
5. Run **Bake Textures**.
6. Select the new `_Baked` mesh.
7. Run **Export Selected Objects**.

The export folder/file name strips `_Baked`, so `SM_Cube1_Baked` exports to `SM_Cube1/SM_Cube1.fbx`.


### Baking tip
Use a small Bake Padding value with compact Smart UVs. Higher padding reduces dark seams, but if UV islands are close together it can cause color bleeding between islands.
