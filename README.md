# Polygon Compare QGIS Plugin

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
1. **From QGIS Plugin Repository** (once published):
   - In QGIS, go to `Plugins > Manage and Install Plugins`.
   - Search for "Polygon Compare" in the `All` tab.
   - Click `Install Plugin`.

2. **From ZIP File**:
   - Download the plugin ZIP file from the [GitHub Releases](https://github.com/AnustupJana/polygon_compare/releases) page.
   - In QGIS, go to `Plugins > Manage and Install Plugins > Install from ZIP`.
   - Select the downloaded ZIP file and click `Install Plugin`.

3. **From Source (for developers)**:
   - Clone or download this repository:
     ```bash
     git clone https://github.com/AnustupJana/polygon_compare.git
     ```
   - Copy the `polygon_compare` folder to your QGIS plugins directory:
     - Windows: `C:\Users\[YourUsername]\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins`
     - Linux: `~/.local/share/QGIS/QGIS3/profiles/default/python/plugins`
     - macOS: `~/Library/Application Support/QGIS/QGIS3/profiles/default/python/plugins`
   - In QGIS, go to `Plugins > Manage and Install Plugins`, enable "Polygon Compare".

4. Restart QGIS to load the plugin.

## Usage
1. **Open the Plugin**:
   - After installation, find the plugin in the QGIS toolbar or under `Plugins > Polygon Compare > Compare Polygon Layers`.
   - Alternatively, open the Processing Toolbox (Ctrl+Alt+T) and locate `Vector Analysis > Compare Polygon Layers`.

2. **Configure Parameters**:
   - **Old Polygon Layer**: Select the original polygon layer.
   - **New Polygon Layer**: Select the updated polygon layer.
   - **Unique ID Field**: Choose a field (e.g., "id") that uniquely identifies features in both layers.
   - **Output Layers**:
     - **Modified Polygons**: Destination for polygons with changed geometries.
     - **Added Polygons**: Destination for new polygons in the new layer.
     - **Deleted Polygons**: Destination for polygons missing from the new layer.

3. **Run the Algorithm**:
   - Click `Run` in the dialog.
   - The plugin will process the layers and produce three output layers, which are automatically added to your QGIS project.
   - Progress and feedback (e.g., counts of added, deleted, and modified polygons) are shown in the Processing Log.

4. **Review Outputs**:
   - Check the output layers in the QGIS Layers panel.
   - Use QGIS tools to analyze or visualize the results (e.g., style the layers to highlight changes).

## Example
- **Input**:
  - Old Layer: `land_parcels_2024.shp` (with field "parcel_id")
  - New Layer: `land_parcels_2025.shp` (with field "parcel_id")
  - Unique ID Field: `parcel_id`
- **Output**:
  - `Modified Polygons`: Parcels with updated boundaries.
  - `Added Polygons`: New parcels added in 2025.
  - `Deleted Polygons`: Parcels removed since 2024.

## Troubleshooting
- **Error: "ID field not found"**:
  - Ensure both input layers have the specified unique ID field.
- **Error: "Layer is not a polygon layer"**:
  - Verify that both input layers are vector polygon layers.
- **Icon not displaying**:
  - Ensure `icon.png` is present in the plugin directory.
- **Plugin not appearing**:
  - Check the QGIS plugins directory and reload the plugin via `Plugins > Manage and Install Plugins`.
- For further issues, check the QGIS Python Console (Ctrl+Alt+P) or Log Messages panel (View > Panels > Log Messages).

## Development
To contribute or modify the plugin:
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/polygon_compare.git
   ```
2. Install dependencies (if any) and ensure `pyrcc5` is available for resource compilation:
   ```bash
   pyrcc5 -o resources.py resources.qrc
   ```
3. Test changes in QGIS by copying the `polygon_compare` folder to the plugins directory.
4. Submit pull requests or report issues on the [GitHub Issues](https://github.com/AnustupJana/polygon_compare/issues) page.

## Metadata
- **Plugin Name**: Polygon Compare
- **Version**: 0.1
- **Author**: Anustup Jana
- **Email**: anustupjana21@gmail.com
- **License**: GNU General Public License v2.0 or later
- **Repository**: [GitHub](https://github.com/AnustupJana/polygon_compare)
- **QGIS Minimum Version**: 3.0

## Acknowledgments
- Built using the QGIS Plugin Builder.
- Powered by the QGIS Processing Framework.

## Contact
For questions, bug reports, or feature requests, contact Anustup Jana at [anustupjana21@gmail.com](mailto:anustupjana21@gmail.com) or open an issue on GitHub.

---
**Copyright (C) 2025 Anustup Jana**
