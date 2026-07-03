# WhatsApp Voice Note Sender

Send OGG audio files as WhatsApp voice notes via WhatsApp Web.

Uses Playwright to drive WhatsApp Web and injects [WPPConnect/wa-js](https://github.com/nicasiomobica/nicasiomobica/wa-js) to send audio as real PTT (push-to-talk) voice notes with waveform.

## Setup

```bash
uv sync
uv run playwright install chromium
```

## Usage

### First-time login (scan QR code)
```bash
uv run python send_whatsapp.py --login
```

### Send voice note(s)
```bash
uv run python send_whatsapp.py 919876543210 audio.ogg
uv run python send_whatsapp.py 919876543210 part1.ogg part2.ogg part3.ogg
```

Phone number should include country code without `+` (e.g. `919876543210`).

## Features

- Sends OGG/Opus files as native WhatsApp voice notes (PTT)
- Automatically splits files exceeding WhatsApp's 16 MB limit
- Sends a text label before each voice note for easy identification
- Supports multiple files in a single command
