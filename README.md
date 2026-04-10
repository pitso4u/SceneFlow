# SceneFlow (Local Video Scene Builder)

SceneFlow is a lightweight, in-browser motion graphics and video scene editor. It provides a drag-and-drop canvas, an interactive timeline, and programmable keyframe animations, bridging the gap between static design tools and full-blown video editors like CapCut.

## Features

- **Real Media Support:** Drop in real images and MP4 video clips directly onto the canvas. Video playback automatically synchronizes with the timeline.
- **Interactive Timeline Scrubbing:** Jump exactly to where you want in the scene by clicking on the timeline tracks. All properties instantly reflect the correct frame state.
- **Keyframe Interpolation Engine:** Move beyond simple entry animations. Elements smoothly interpolate their position, scale, and opacity over time based on local keyframes using the built-in linear interpolation (`lerp`) engine.
- **Polished Properties Panel:** Adjust X/Y coordinates, width, height, colors, and the entry/exit timestamps of selected elements easily in the property inspector.
- **Export to JSON:** Export your structured project data to a standard format, which can be hooked up to a Node.js/Puppeteer/FFmpeg pipeline for offline high-quality video rendering.

## How to Run

Because this is a completely vanilla HTML/CSS/JS frontend application, no build tools or servers are required!

1. Clone or download the repository.
2. Double-click on `index.html` to open it in your preferred modern web browser.
3. Start dropping elements onto the canvas and hitting **Play**.

## Exporting for Rendering

Clicking the **Export JSON** button generates a `sceneflow-project.json` file. This format defines exact positioning, opacity, timestamps, and keyframe data for all elements layer-by-layer. 

To convert this JSON to a real `.mp4` file, the planned backend rendering pipeline uses headless Chromium to render the frames, and piping those snapshots directly into `ffmpeg`. 

*(Backend rendering scripts are in active development).*
