# BioSynth SD Manager

A minimal local web interface for downloading files from a Teensy 4.1 SD card over USB serial.

## Requirements

- Teensy firmware implementing:
  - `BIOSYNTH_SD_LIST`
  - `BIOSYNTH_SD_GET<TAB>filename`
- A browser with Web Serial support. Current Chrome/Chromium is the safest first test.
- The Teensy connected by USB.
- No other program holding the Teensy serial port open (Arduino Serial Monitor, Teensy Monitor, miniterm, etc.).

## Run locally

From this folder:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

Click **Connect BioSynth**, choose the Teensy device, and the page should list SD-card files.

## Notes

The page does not upload files to the internet - Transfers happen locally between the Teensy and your browser.

Because Web Serial requires a secure context, use `localhost` for local testing or HTTPS if you later deploy this page to a server.
