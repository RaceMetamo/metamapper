# MetaMapper

**Browser-based projection mapping and generative animation tool.**

MetaMapper lets you map projection surfaces (by hand on site, from a mask image, or automatically from a webcam), fill each surface with generative effects, images, video or live feeds from other tools, modulate everything with LFOs or live audio, and record the result. It runs as a single HTML file with no install, no build step and no dependencies.

Developed by [Metamo Industries](https://metamoind.com) for the **Haji Lane Projection Hub at The Bridge Gallery (TBG)**, 23 Haji Lane, Singapore.

---

## Launch

**[Open MetaMapper →](https://racemetamo.github.io/metamapper/)**

Works in Chrome, Edge and other Chromium browsers. It opens with The Bridge Gallery's wall already mapped, so you can switch to **ANIMATE** and start designing straight away.

---

## Features

### Mapping
- **Polygon regions and open splines**, traced by clicking over a reference mask image
- Drag points, right-click to delete a point, reopen closed shapes, layer reordering, duplicate, solo/mute
- **Rename** regions and **group** them, so separate shapes at the same depth share every effect setting
- **Undo / redo** for all shape and layer changes
- Labels shown in the centre of each shape while editing

### On-site mapping with a projector
- **📽 Projector** opens a second window for the projector. In Chrome it can move itself onto the second display; double-click it or press F for fullscreen
- In Edit mode the projector shows each shape as a flat colour with outlines and labels, plus a **crosshair** following your mouse, so you can see exactly where every point lands on the wall
- Optional **light grid** (adjustable divisions) for finding your way around the projector frame
- Drag points on **either screen**: the laptop or the projector itself
- **MAP / live map** keeps outlines, crosshair and point editing on top of the running animation, so you can fine-tune alignment with content playing
- Keyboard nudging for precise alignment: arrows move the selected point 1px (Shift 10px, Alt ¼px), Tab selects the next point, Delete removes it
- Grid, crosshair, outlines and the fps counter never appear in recordings or stills, only the content does

### Scan / auto-mask
Builds regions automatically instead of tracing by hand.
- **From a mask image:** loads your template and traces each panel. In Colour mode, touching panels of different colours come out as separate shapes (the TBG template traces into all 8 panels in one click)
- **From a webcam on site:**
  1. **Calibrate.** Auto flashes the projector black then white and finds the projected frame in the camera image; or drag the four corners by hand onto the bright corner blocks the projector shows. Calibration is remembered on that computer
  2. **Detect.** The projector lights the wall white so the camera sees the real surfaces. Choose **Brightness**, **Colour** or **Edges / lines** mode and tune threshold, blur, size limits and point simplification until the outlines match
  3. **Add as regions** (or Replace all), then refine the points on the projector
- Freeze a camera frame, choose between multiple cameras

### Fill effects
Noise, Scan Lines, Pulse, Breathe, Rain, Static, Plasma, Gradient, Grid, Ripple, Stripes, Solid, Checker, Wave, Voronoi (with cell count and seed for shifting fracture patterns), **Image**, **Video** and **Source** (live feeds, see below).

Every fill has hue, intensity, speed, scale, angle, opacity and phase controls.

### Images, video and live sources
- **Image** and **Video** fills per region, with Cover / Contain / Tile fit and X/Y position. Fill Hue tints the media, Fill Int sets brightness, and Scale / Angle / Opacity manipulate it like any other effect. Video has play/pause, mute and restart
- **Live sources** feed regions from outside MetaMapper:
  - **Unlimiter tools:** opens a tool page in its own window and pipes its canvas in live
  - **Tab / window capture:** any browser tab, app window or screen (TouchDesigner, Resolume previews, anything)
  - **Camera:** a webcam as a live texture

### Edge effects
Chasing Pulse, Particle Flow, Strobe, Maze, Neon Glow, Animated Dashes, Double Stroke and Dotted, each with hue, speed and width.

### Text
- Text per region or spline in three modes: **Center**, **Follow Edge** (text travels around the shape or along the spline) and **Scroll**
- Font choice, size, speed, offset from the path, repeat count, outline and reverse direction
- Characters skip rather than pile up at tight corners

### Modulation and audio
Every major parameter can be driven by an LFO (Sine, Triangle, Sawtooth, Square, Noise) or by live audio from the microphone (Bass, Mid, High bands), with rate and depth per parameter. Post effects have their own modulation too.

### Post-processing and global controls
- Trails, Bloom, Vignette, Chromatic Aberration
- Global speed, brightness, blackout, hue shift, saturation, contrast and a four-colour palette
- Per-region blend modes: Normal, Add, Multiply, Screen, Overlay, Difference
- Horizontal and vertical **mirror** for symmetrical facades

### Performance tools
- **Tap tempo** sets global speed from your BPM
- **Randomize** all regions in one click, or auto-randomize every 2 to 32 seconds
- **Copy / paste style** between regions
- Render at ½× resolution for smooth editing, 1× for final output; **Unmask** drops the reference image for extra performance

### Recording and export
- **MP4** recording straight from the browser (WebM fallback) and **PNG** stills
- **JSON** project files: download a project and load it back later or on another machine (includes images; video and live sources are re-added per session)
- **Presets** saved in the browser
- **SVG** of the traced shapes, **OBJ** mesh with a canvas-bounds reference quad, and a **Blender Python script** that sets up an orthographic camera matching your canvas

---

## Quick start

### Design for The Bridge Gallery wall
1. Open MetaMapper and click **START CREATING**
2. Switch **EDIT → ANIMATE**
3. Pick fills, edges, text, colours and modulation for each region in the side panel
4. Record with **⏺** or grab a still with **📷**
5. Submit through the [submission form](https://docs.google.com/forms/d/e/1FAIpQLScgH7YNImUIldbjQlcJnveA_4H4z2rWt9FdS0cnP5mekzZEUA/viewform)

### Map a new surface from a mask image
1. **Mask** → load your template image
2. **Scan** → Source: Loaded mask image → Show scan preview → Mode: Colour
3. Adjust until the yellow outlines match, then **Add as regions**

### Map a surface on site
1. Connect the projector as a second display and click **📽 Projector**; make it fullscreen on the projector
2. Either trace shapes by hand while watching the projector, or use **Scan** with a webcam: Camera on → Calibrate (Auto) → Show scan preview → tune → Add as regions
3. Refine points by dragging on either screen or nudging with the arrow keys
4. Switch to ANIMATE and turn on **MAP** to fine-tune with content running

### Use an Unlimiter tool as a layer
1. Set a region's Fill to **Source**, open the Source menu and pick the tool under *Open an Unlimiter tool* — it opens in its own window and the region uses it straight away (or add it first from **Sources → + Unlimiter tool**)
2. Adjust the tool in its own window; the region updates live
3. The address box in **Sources** says where the tools live — a folder (default `../Unlimiter/`) or one page

---

## Good to know
- **Tab / window capture shows Chrome's sharing bar.** Chrome marks any shared tab with a "sharing this tab" bar and shrinks that tab to fit it; a page can't turn it off. Press **Hide** on the bar, or use the Unlimiter tool route above, which reads the tool's canvas directly and shows no bar or prompt
- **Same-site rule for tools.** + Tool only works when the tool and MetaMapper are on the same site (both on racemetamo.github.io works; a downloaded copy of MetaMapper doesn't). For anything else, use **+ Tab / window**
- **Keep feeding windows visible.** Browsers slow down hidden windows, so keep tool windows open and on screen
- **Camera scanning** works best in a dim space with the camera roughly facing the wall. Expect to tune Threshold and Blur on site
- **Pop-ups** must be allowed for the projector and tool windows
- Live sources and videos aren't saved in JSON files; re-add them after reloading

---

## Using MetaMapper with other software

- **SignCloud / media servers:** record MP4 at 1× resolution and upload it
- **Resolume:** capture the projector window in OBS with the [Spout2 plugin](https://github.com/Off-World-Live/obs-spout2-plugin) and pick it up as a Spout source
- **Blender:** export OBJ plus the Blender script, import the OBJ, run the script for a pixel-aligned orthographic camera, then extrude and light the panels
- **TouchDesigner:** load the OBJ into a File In SOP and use an orthographic Camera COMP at your canvas size
- **After Effects:** import the recorded MP4 directly

---

## The Bridge Gallery

The Bridge Gallery is a permanent projection mapping installation and creative exhibition space at [23 Haji Lane](https://maps.google.com/?q=23+Haji+Lane+Singapore), in the heart of Kampong Glam. It is both a living canvas for projection art and a platform for opening up projection mapping tools and workflows to the wider creative community.

We're always looking for new content for the wall. Template files (mask, OBJ, Blender setup) are in the [template folder](https://drive.google.com/drive/folders/1FgiCvftnAhpEMHPaC3dgRQcePjTkURjQ?usp=drive_link), and work can be sent in through the [submission form](https://docs.google.com/forms/d/e/1FAIpQLScgH7YNImUIldbjQlcJnveA_4H4z2rWt9FdS0cnP5mekzZEUA/viewform).

---

## Technical notes
- Single self-contained HTML file; all rendering with the Canvas 2D API
- Content renders to an off-screen canvas; the operator view, projector window and recordings each take their own copy, so editing overlays never leak into output
- Shape coordinates are stored as 0–1 values, so projects work at any resolution
- Audio via the Web Audio API; recording via MediaRecorder; cameras and tab capture via getUserMedia / getDisplayMedia; projector placement via Chrome's Window Management API
- Webcam calibration uses a four-corner perspective (homography) transform; detection uses thresholding, colour-aware region labelling, Sobel edges, contour tracing and Douglas–Peucker simplification

---

## Credits

**MetaMapper** by [Metamo Industries Pte. Ltd.](https://metamoind.com), a Singapore-based immersive media studio specialising in projection mapping, interactive installations, XR and real-time engine work.

- Website: [metamoind.com](https://metamoind.com)
- Instagram: [@metamo_industries](https://www.instagram.com/metamo_industries)
- The Bridge Gallery: [@thebridgegallery.sg](https://www.instagram.com/thebridgegallery.sg)

---

## License

© Metamo Industries Pte. Ltd. All rights reserved.
