# Polygon Compare QGIS Plugin 
![Diagram of the System](https://github.com/AnustupJana/PolygonCompare-plugin/blob/main/icon.png?raw=true)

## Description
**Polygon Compare** is a QGIS plugin that compares two vector polygon layers to identify added, deleted, and modified polygons based on a unique ID field and their geometry. It produces three output layers:
- **Added Polygons**: Features present in the new layer but not in the old layer.
- **Deleted Polygons**: Features present in the old layer but not in the new layer.
- **Modified Polygons**: Features with the same unique ID in both layers but different geometries.

This plugin is designed for GIS users who need to track changes between two versions of a polygon dataset, such as in urban planning, environmental monitoring, or land use analysis.

## Features
- Compares two polygon layers using a unique ID field and geometry.
- Generates three output layers: Added, Deleted, and Modified Polygons.
- Integrates seamlessly with the QGIS Processing Toolbox.
- Provides detailed feedback during processing, including counts of added, deleted, and modified features.
- Supports validation checks for layer types, geometry validity, and ID field presence.

## Requirements
- **QGIS Version**: 3.0 or later
- **Operating System**: Windows, macOS, or Linux
- **Dependencies**: None (uses QGIS core and processing libraries)

## Installation
1. **From QGIS Plugin Repository**:
   - In QGIS, go to `Plugins > Manage and Install Plugins`.

![Diagram of the System](https://github.com/AnustupJana/PolygonCompare-plugin/blob/main/doc/1st_Plugin.png?raw=true)
   - Search for "Polygon Compare" in the `All` tab.
   - Click `Install Plugin`.
     
![Diagram of the System](https://github.com/AnustupJana/PolygonCompare-plugin/blob/main/doc/2nd_Install.png?raw=true)
     

2. **From ZIP File**:
   - Download the plugin ZIP file from the [GitHub Releases](https://github.com/AnustupJana/PolygonCompare-plugin/archive/refs/heads/main.zip) page.
   - In QGIS, go to `Plugins > Manage and Install Plugins > Install from ZIP`.
   - Select the downloaded ZIP file and click `Install Plugin`.

3. **From Source (for developers)**:
   - Clone or download this repository:
     ```bash
     git clone https://github.com/AnustupJana/PolygonCompare-plugin.git
     ```
   - Copy the `polygon_compare` folder to your QGIS plugins directory:
     - Windows: `C:\Users\[YourUsername]\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins`
     - Linux: `~/.local/share/QGIS/QGIS3/profiles/default/python/plugins`
     - macOS: `~/Library/Application Support/QGIS/QGIS3/profiles/default/python/plugins`
   - In QGIS, go to `Plugins > Manage and Install Plugins`, enable "Polygon Compare".


## Usage
1. **Open the Plugin**:
   - After installation, find the plugin in the QGIS toolbar or under `Plugins > Polygon Compare > Compare Polygon Layers`.

![Diagram of the System](https://github.com/AnustupJana/PolygonCompare-plugin/blob/main/doc/3rd_Show_Plugin.png?raw=true)

   - Alternatively, open the Processing Toolbox (Ctrl+Alt+T) and locate `Vector Analysis > Compare Polygon Layers`.

1. **Configure Parameters**:
   - **Old Polygon Layer**: Select the original polygon layer.
   - **New Polygon Layer**: Select the updated polygon layer.
   - **Unique ID Field**: Choose a field (e.g., "id") that uniquely identifies features in both layers.
   - **Output Layers**:
     - **Modified Polygons**: Destination for polygons with changed geometries.
     - **Added Polygons**: Destination for new polygons in the new layer.
     - **Deleted Polygons**: Destination for polygons missing from the new layer.

2. **Run the Algorithm**:
   - Click `Run` in the dialog.
   - The plugin will process the layers and produce three output layers, which are automatically added to your QGIS project.
   - Progress and feedback (e.g., counts of added, deleted, and modified polygons) are shown in the Processing Log.
  
![Diagram of the System](https://github.com/AnustupJana/PolygonCompare-plugin/blob/main/doc/4th_Run_Plugin.png?raw=true)

![Diagram of the System](https://github.com/AnustupJana/PolygonCompare-plugin/blob/main/doc/5th_Get_Output.png?raw=true)

3. **Review Outputs**:
   - Check the output layers in the QGIS Layers panel.
   - Use QGIS tools to analyze or visualize the results (e.g., style the layers to highlight changes).

![Diagram of the System](https://github.com/AnustupJana/PolygonCompare-plugin/blob/main/doc/6th_Check_Output.png?raw=true)

## Example
- **Input**:
  - Old Layer: `land_parcels_2024.shp` (with field "parcel_id")
  - New Layer: `land_parcels_2025.shp` (with field "parcel_id")
  - Unique ID Field: `parcel_id`
- **Output**:
  - `Modified Polygons`: Parcels with updated boundaries.
  - `Added Polygons`: New parcels added in 2025.
  - `Deleted Polygons`: Parcels removed since 2024.

## Contact
For questions, bug reports, or feature requests, contact Anustup Jana at [anustupjana21@gmail.com](mailto:anustupjana21@gmail.com) or open an [issue](https://github.com/AnustupJana/PolygonCompare-plugin/issues) on GitHub.

---
**Copyright (C) 2025 Anustup Jana**
