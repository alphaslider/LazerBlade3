LAZERBLADE
Browser-Native Digital Audio Slicer & Editor

Lazerblade is a lightweight, zero-dependency digital audio workstation built for fast sample chopping and wave editing. Designed with a strict single-file architecture, it bypasses heavy modern frameworks in favor of raw HTML5, CSS3, and Vanilla JavaScript, executing all digital signal processing directly within the browser.

Technical Details
Audio Engine: Built on the native Web Audio API (AudioContext). It utilizes decodeAudioData for memory-efficient loading and custom Float32Array buffer manipulation for non-destructive cutting, copying, and pasting.

Rendering System: The waveform visualization is driven by HTML5 <canvas> and synchronized with requestAnimationFrame for fluid, low-latency playhead tracking and zoom rendering.

Zero-Dependency Architecture: Lazerblade requires no build steps, package managers, or server-side processing. It runs entirely client-side, making it ideal for offline use or low-spec hardware like Chromebooks.

Client-Side Encoding: Standard 16-bit PCM RIFF WAV files are constructed purely in memory using JavaScript DataView. Multi-slice exports are packaged into ZIP archives dynamically by writing binary local file headers and central directory records directly to a Blob.

UI/UX: The interface leverages a dark, hardware-inspired aesthetic with dynamic CSS variables (--accent-color) that map to user selections in real-time, completely avoiding external UI libraries.

User Manual
1. Basic Transport & Navigation
Loading Audio: Click File > Open Audio... to load any supported audio file from your local disk.

Playback: Use the PLAY and STOP buttons, or click anywhere on the waveform canvas to seek.

Zoom & Scroll: Use the Mouse Wheel over the canvas to zoom in and out. Hold Shift + Mouse Wheel to scroll horizontally across the waveform.

Zero-Cross Snapping: Enabled by default in the Select menu, this forces all selections and slice markers to snap to the nearest zero-crossing point to prevent audio clicks and pops.

2. Loop Selection & Editing
Selecting Audio: Click and drag the S (Start) or E (End) markers on the canvas to define your active window.

Looping: Toggle the LOOP button to continuously cycle playback within your defined Start and End markers.

Clipboard Operations: Open the Edit menu to Cut, Copy, or Paste audio buffer data. The Undo function supports up to 10 sequential history states.

3. Chop Mode (Slicing)
Toggle the CHOP button to switch from standard loop selection to multi-slice mode.

Adding Markers: Click anywhere on the waveform to drop a numbered slice marker.

Moving Markers: Click and drag an existing marker to adjust its position.

Trigger Mode: Check the TRIGGER box to turn slice markers into playheads. Clicking near a marker will instantly play that specific slice.

Deleting Markers: Check the DEL CHOP box, then click any existing marker to remove it.

4. Exporting
Export Selection: Available under File > Export Selection. This renders your currently selected window (between the Start and End markers) as a standard .wav file.

Export Slices: Available under File > Export Slices (ZIP). This takes all active slice markers, splits the audio buffer at those points, encodes each slice as a distinct .wav file, and downloads them bundled within a .zip archive.
