# A Reaper/FMOD Framework for Adaptive Music

A toolchain for composers and game audio designers to create adaptive music with horizontal re-sequencing directly within Reaper, and automatically export and assemble the corresponding FMOD project.

The framework consists of two components:
- **Reaper script** — automates asset rendering (including release tails for seamless transitions) and exports the transition graph.
- **FMOD script** — automatically generates an FMOD event embedding the horizontal re-sequencing logic from the generated assets and graph.
---

## Installation

### Reaper Script — TransitionsRenderer

1. Download the `TransitionsRenderer` folder from this repository.
2. Locate your Reaper Scripts folder by opening Reaper and navigating to **Options > Show REAPER resource path in Explorer/Finder**. Inside the opened folder, go to the `Scripts` subfolder.
3. Copy the `TransitionsRenderer` folder into that `Scripts` folder.
4. Back in Reaper, go to **Actions > Show action list**, click **ReaScript: Load**, and load the main script from the folder.

### FMOD Script — TransitionsAssembler

1. Download `TransitionsAssembler.js` from this repository.
2. Copy it to the FMOD Studio scripts folder for your OS:
   - **Windows**: `%USERPROFILE%\Documents\FMOD Studio\Scripts\`
   - **macOS**: `~/Documents/FMOD Studio/Scripts/`
   - **Linux**: `~/Documents/FMOD Studio/Scripts/`
3. Restart FMOD Studio. The script will appear under the **Scripts** menu.

---

## Usage

### Reaper Script — TransitionsRenderer

Once installed, the renderer is executed from **Actions > Show action list** by selecting the corresponding action, on a project containing the regions to be rendered.

![TransitionsRenderer GUI](docs/renderer_gui.png)

The GUI includes a transition graph matrix in the upper section, allowing users to specify the transition graph graphically. Users can choose to include all regions in the project or only those selected in the region render matrix. Once the transition graph is defined, the lower buttons enable users to either:
- **Render assets and export** the graph to a JSON file, or
- **Export the graph only** — useful when assets have already been rendered and only the graph needs to be updated.

The **Settings** menu provides configuration options:
- Output path and JSON filename
- Prefixes/suffixes for asset naming
- Maximum render tail duration
- Trailing silence threshold
- Whether to include assets in auxiliary tracks
- Whether to work on a project copy
- Whether to expand default edges

### FMOD Script — TransitionsAssembler

On an empty FMOD project, run the script from **Scripts > TransitionsAssembler**. The script will automatically generate a complete event containing:
- All music regions as timeline segments
- The transition logic between regions
- A labeled parameter driving the region switching

The event is immediately ready for integration into the game engine.

> **Note:** Region parameter labels may appear overlapped in the FMOD UI — this is a display issue only and does not affect functionality.

A demonstration video showcasing the scripts in action is available [here](https://drive.google.com/file/d/1N2CV54FB5GoNftb0w1jMcDUh9MzEoQg6/view?usp=sharing).

---

## Citation

> _Citation coming soon._