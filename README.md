# MCS — Musical Composition System

A lightweight, Python-based music composition and sound synthesis application originally developed for **Nokia Symbian S60**.

MCS combines an additive synthesizer, an event-based sequencer and a software audio renderer into a compact music production environment.

## Features

- **Additive synthesis** — 24-harmonic waveform construction with editable harmonic parameters.
- **Musical sequencer** — Event-based composition with pitch, duration and octave editing.
- **Procedural generation** — Randomized note generation using predefined pitch intervals.
- **Equal temperament** — Frequency calculation and an 88-note tuning table.
- **Audio rendering** — Software-generated PCM audio with configurable sample rate and bit depth.
- **WAV export** — RIFF/WAVE file construction from rendered audio.
- **Preset storage** — Binary serialization of synthesizer parameters and sequences.
- **Graphical interface** — Native Symbian S60 menus, forms, canvas rendering and keyboard interaction.

## Architecture

The application is organized around three principal subsystems:

| Subsystem | Responsibility |
|---|---|
| Main application | Interface, navigation, playback and subsystem coordination |
| Synthesizer | Harmonic editing and waveform generation |
| Sequencer | Musical event editing and procedural sequence generation |

Supporting modules provide tuning, audio rendering, WAV/RIFF processing, file navigation and shared resources.

### Audio pipeline

```text
Synthesizer parameters
        |
        v
Waveform generation <--- Tuning table
        |
        v
Sequencer events
        |
        v
Tone rendering
        |
        v
Raw PCM samples
        |
        v
RIFF/WAV encoding
        |
        v
Audio playback
```

## Technical Details

- **Language:** Python 2
- **Platform:** Nokia Symbian S60
- **Synthesis:** Additive, periodic waveform generation
- **Harmonics:** 24
- **Sequencing:** 48 ticks per quarter note
- **Tuning:** 12-tone equal temperament
- **Audio format:** PCM / RIFF-WAVE
- **Storage:** Binary `.dat` presets and sequence files

## Project Status

The source represents an early-stage implementation of a compact software synthesizer and sequencer.

Some functionality is incomplete, including sequence loading, scale editing, parts of the import/export interface and 8-bit audio rendering.

The original platform-specific dependencies (`appuifw`, `e32`, `graphics`, `audio`, etc.) make the application incompatible with modern desktop Python without substantial adaptation.

## Background

MCS explores the integration of sound synthesis, musical composition and audio rendering within the resource constraints of an early mobile computing platform.

Its modular separation of synthesis, sequencing and rendering provides the foundation for understanding and potentially porting the original application.
