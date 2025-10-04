# MayaAttractDeformer

**MayaAttractDeformer** is a custom Maya node that morphs a mesh toward a separate target object, as if the target acts as a magnet pulling the surface of the mesh. This is useful for creating attraction-based deformations, morphing effects, or dynamic mesh interactions inside Autodesk Maya.

## Features

- **Attracts/Morphs mesh vertices toward a separate object (target)**
- **Fully compatible with recent versions of Maya**
- **Integrates as a native deformer node for non-destructive workflows**

## How It Works

The AttractDeformer node computes the displacement for each vertex of a source mesh, pulling it toward the corresponding location on a target object. The strength and falloff of the attraction can be customized via node attributes.

## Installation

1. **Build the Plugin:**
    - Ensure you have the Maya API and development environment set up.
    - Clone or download this repository.
    - Link against the Maya API when compiling.

2. **Load the Plugin in Maya:**
    - Copy the compiled plugin (`.mll`/`.so`/`.bundle`) to your Maya plugins directory.
    - In Maya, go to **Windows > Settings/Preferences > Plug-in Manager** and load the plugin.

## Usage

1. Select the mesh you want to deform.
2. Add the AttractDeformer node via the Maya command or UI.
3. Specify the target object (the "magnet" mesh) in the node’s attributes.
4. Adjust parameters such as attraction strength and falloff to achieve the desired effect.

### Example (MEL)

```mel
// Example: Apply AttractDeformer to 'sourceSphere', targeting 'targetLocator'
select sourceSphere; deformer -type attractordeformernode;
connectAttr -force targetLocator.translate attractordeformernode1.targetPosition
```

## Requirements

- Autodesk Maya (2020 or newer recommended)
- Maya C++ API (for building the plugin)
- C++ Compiler compatible with your Maya version

## License

[MIT License](LICENSE)
