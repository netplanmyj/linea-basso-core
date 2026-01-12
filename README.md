# LineaBasso Core

**LineaBasso Core** is an open-source audio analysis engine that detects and extracts **bass lines** from audio files and converts them into **note-level data or MIDI**.

This repository contains the **core signal processing and analysis logic** used by the LineaBasso app.

---

## What this project does

Given an audio file (wav / mp3):

1. Separates the **bass track** from the mix
2. Estimates pitch (fundamental frequency)
3. Converts pitch over time into:
   - Note names (e.g. `E2`, `G2`, `Bb2`)
   - Start time and duration
   - Optional MIDI output

**Score notation is intentionally not used.**

---

## Input / Output

### Input
- Audio file (`wav`, `mp3`)
- User-provided or recorded audio only

### Output
- JSON note data

```json
[
  { "pitch": "E2", "start": 0.52, "duration": 0.48 },
  { "pitch": "G2", "start": 1.04, "duration": 0.36 }
]
```

- MIDI file (optional)

---

## Core technologies

- **Demucs** — source separation (bass extraction)
- **CREPE** — pitch (f0) estimation
- **Python** — orchestration and post-processing

This project focuses on **single-note bass lines**.  
Ghost notes, chords, and advanced techniques may not be detected accurately.

---

## Design philosophy

- Bass-focused (not general transcription)
- Practical accuracy over theoretical perfection
- Designed for **editing and correction by humans**
- UI and app logic are intentionally out of scope

---

## Project status

🚧 **Work in progress**

Current goal:
- Proof of Concept (PoC)
- End-to-end pipeline:
  audio → bass → pitch → notes → JSON / MIDI

---

## License

MIT License

---

## Disclaimer

This project does **not** provide or distribute copyrighted audio.  
Users are responsible for the audio files they analyze.
