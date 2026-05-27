# NeuroForge

NeuroForge is a single-file Three.js application for generating, visualizing, analyzing, and exporting synthetic neuron morphologies. It builds recursive neurite skeletons, converts them into dense 3D point clouds, animates flow formation, simulates signal propagation, and exposes morphometric analysis tools such as Sholl profiles and branch-order charts.

## Features

- Procedural synthetic neuron generation with seeded randomness.
- Cell-style presets for pyramidal, Purkinje, stellate, bipolar, motor, chandelier, granule, apical tuft, basket, Martinotti, retinal ganglion, mitral, astrocyte-like, and multi-neuron MICrONS-style patches.
- Morphology controls for complexity, tortuosity, branch spread, taper, neuron count, spine density, bouton density, and growth bias.
- Real-time 3D visualization with OrbitControls, bloom, depth-of-field, skeleton overlays, Sholl rings, soma spheres, synapse markers, ambient particles, and multiple color modes.
- Flow-matching-style formation animation from noisy source points into the generated morphology.
- Signal propagation overlay with axon/dendrite/glia-specific conduction behavior.
- Morphometrics dashboard with total points, segments, terminal tips, cable length, bifurcations, branch order, extent, synapse markers, fractal estimate, Sholl peak, and branch entropy.
- Research Compass panel for a compact generated-morphology signature.
- Learn tab with curated video, dataset, SWC, Sholl analysis, connectomics, and computational-neuroscience resources.
- Export support for JSON, SWC, OBJ, PLY, PNG screenshots, 4K screenshots, and Markdown research reports.

## Running Locally

The app is contained in `index.html`. You can open it directly in a browser, but running a local static server is better for browser security and testing.

```powershell
cd "C:\Users\kai99\Desktop\New folder"
python -m http.server 4173 --bind 127.0.0.1
```

Then open:

```text
http://127.0.0.1:4173/index.html
```

The app loads external Three.js and font assets from CDNs, so an internet connection is recommended.

## Basic Workflow

1. Choose a preset in the Generate tab.
2. Adjust morphology parameters such as complexity, spine density, bouton density, and growth bias.
3. Click Generate to create a new morphology.
4. Use Visualize to change point size, bloom, color mode, overlays, and Sholl rings.
5. Use Analyze to inspect morphometrics, Sholl profile, branch-order distribution, and the Research Compass.
6. Use Learn to search relevant videos, datasets, standards, and research resources.
7. Use Export to save morphology data, screenshots, or a Markdown report.

## Export Formats

- `JSON`: full NeuroForge metadata, parameters, point cloud, statistics, and SWC node data.
- `SWC`: morphology skeleton in SWC-style node format with unique IDs across multi-neuron scenes.
- `OBJ`: point-cloud vertices for generic 3D tooling.
- `PLY`: colored point-cloud export.
- `PNG`: current viewport screenshot.
- `4K PNG`: higher-resolution screenshot.
- `Markdown Report`: concise generated-morphology research summary.

## Research Anchors

The app includes links and UI concepts inspired by public neuroscience resources:

- NeuroMorpho.Org for empirical neuron morphology archives.
- Allen Cell Types Database for morphology, electrophysiology, and transcriptomic context.
- MICrONS and FlyWire for connectomics-scale structure.
- SNT and ImageJ Sholl tools for arbor analysis.
- INCF/SWC documentation for morphology interchange.
- Computational-neuroscience lectures and tutorials from MIT OCW, Neuromatch, HHMI BioInteractive, Khan Academy, and Bernstein Network.

## Development Notes

- This is currently a single static HTML file with embedded CSS and JavaScript.
- There is no build step, package manager, or framework.
- Keep feature additions data-driven where possible, especially presets and Learn-tab resources.
- Dispose Three.js geometries/materials when replacing large meshes to avoid GPU memory growth.
- Prefer deterministic seeded randomness for generated morphology so presets are reproducible.

## Verification

Recently verified locally at:

```text
http://127.0.0.1:4173/index.html
```

Checks performed:

- WebGL canvas renders.
- Generate, Visualize, Analyze, Learn, and Export tabs exist.
- Learn search filters resources correctly.
- Apical Tuft preset generates successfully.
- Synapse markers and new morphometrics populate.
- Browser console reports no errors during the tested flows.
