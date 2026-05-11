# Morse Camera Decoder

Browser-based Morse code decoder using your device camera.
Standards-compliant with **ITU-R M.1677-1** timing
(dot=1U, dash=3U, intra-char=1U, inter-char=3U, inter-word=7U).

Point the camera at any standards-compliant optical Morse beacon
(blinking flashlight, an LED, a phone screen, the M5 Cardputer
companion app, …) and watch the decoded text appear live.

## Usage

1. Open the deployed page in a modern browser
   (Chrome, Safari, Firefox — must be served over HTTPS).
2. **Start camera** → grant camera permission.
3. Aim the camera so the flashing light fills the yellow ROI box.
4. **Start decoding** when you're ready — this avoids picking up
   environmental light noise before the transmission begins.
5. Begin transmitting. Decoded text appears in real time;
   estimated WPM and unit time are shown for diagnostics.

The decoder auto-calibrates the unit-time from the first few ON
pulses, so it works with any speed (typically 5–25 WPM).

## Local development

```bash
python3 -m http.server 8000
# http://localhost:8000
```

Camera APIs require a secure context, so plain HTTP only works on
`localhost`. For LAN testing from a phone, run an HTTPS server with
a self-signed cert (see `serve.py` in the companion Cardputer repo).
