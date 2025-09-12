# usdshadeview

A usdview plugin for inspecting UsdShade networks.

<p align="middle">
  <img width="1293" height="1060" src="https://github.com/user-attachments/assets/315b4e20-ca0c-41ba-85a0-8641f68ac0e2" />
</p>

## Installation

Copy the `lib` and `plugin` directories into your USD installation directory.

For [Advanced Instructions](#advanced-installation) see below.

## Features

### 1. Node Graphs

usdshadeview visualizes [UsdShade NodeGraphs](https://openusd.org/release/api/class_usd_shade_node_graph.html) and Materials (which are specialized node graphs) in an interactive Qt dialog:

<p align="middle">
  <img width="1959" height="559" src="https://github.com/user-attachments/assets/462e8cc8-4006-4bf7-b89d-4bf4dd92953f" />
</p>

The dialog can be shown by **right clicking** a prim of one of both types, which brings up a new option in the context menu:

<img width="484" height="330" src="https://github.com/user-attachments/assets/6a2287e6-2233-4426-a42d-bf151e1b6077" />

The network shown in the dialog has a layout depending on network topology, and node colors are based on the classification (USDA, MaterialX, MDL, OSL, node graph, unknown). Child node graphs can be entered using the "E" button.

It is also possible to **right click** value widgets, which exposes following actions:

<img width="277" height="144" src="https://github.com/user-attachments/assets/73cc5269-6fff-486d-9099-698174e35c95" />

In the main graph dialog, the menu bar offers following features:
- _View_ → _Filter Output_: filter nodes and connections to a single output
- _Tools_ → _Bake to Texture_: (only for MaterialX materials) invoke UsdBakeMtlx
- _Tools_ → _Export as Image_: save the scene with a transparent background

**Note:** To display thumbnails for EXRs, the _OpenImageIO_ python package has to be additionally installed.

### 2. Node Def Info

Clicking the "?" button of a node widget opens up the node definition dialog which lists all inputs and outputs with their respective documentation.

<img width="752" height="454" src="https://github.com/user-attachments/assets/2f00e32c-1ce3-488f-bdfb-6377c2589fb4" />

The information is only available for nodes registered in the Sdr registry.

### 3. Sdr Node List

A list of all nodes in the Sdr registry can be accessed from the usdview menu bar _Window_ → _Sdr Nodes_ submenu.

<img width="606" height="399" src="https://github.com/user-attachments/assets/90579ab5-1bce-4d20-91c2-f3ccf12d3709" />

Clicking on an entry brings up its node definition dialog.

## Compatibility

I have tested this plugin on Windows and macOS with PySide2 and PySide6, and Python 3.7, 3.9 and 3.11.

It has been verified to be compatible with OpenUSD versions down to v22.11.

## Advanced Installation

The plugin can be used outside of the build tree by setting following environment variables:
* `PYTHONPATH` to include `<REPO_ROOT>/lib/python`
* `PXR_PLUGINPATH_NAME` to include `<REPO_ROOT>/plugin/usd/usdshadeview/resources`

## License

Apache 2.0
