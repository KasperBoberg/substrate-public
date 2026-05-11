# Substrate

**Physically based spectral simulation of analog photography.**

Substrate is a closed-source research and production tool for end-to-end simulation of the analog photographic process — from camera RAW capture through virtual negative, optical printing, and final scan. The simulation is grounded in spectroscopic data from manufacturer datasheets and models the physical and chemical behaviour of real photographic materials, including dye absorption spectra, characteristic curves, colour couplers, halation, and grain.

> This repository is a public reference. The source code is maintained privately.

---

## What it does

Starting from a linear scene-referred image, Substrate passes it through a configurable pipeline:

- **Negative exposure** — spectral sensitivity curves, layer cross-talk, masking and inhibitor couplers
- **Chemical development** — characteristic density curves, coupler diffusion, local contrast effects
- **Optical printing** — virtual colour enlarger with dichroic filter control, illuminant selection, pre-flash
- **Scan** — configurable scanner spectral response, sharpening, output colour space

The result is a rendering that reflects the structure and behaviour of specific film stocks and print papers rather than a generic "film look."

---

## Key features

- **GPU-accelerated pipeline** — full-resolution processing at interactive speeds
- **Modern desktop GUI** — clean, responsive interface designed for iterative creative work
- **Spectral throughout** — all colour calculations operate in spectral space, with RGB only at input and output
- **Film grain** — stochastic grain model operating on the virtual negative
- **Halation** — per-channel scattering and halation with tunable radius and strength
- **Profile system** — film and paper profiles built from published datasheet curves

---

## Tech stack

| Layer | Technology |
|---|---|
| Core simulation | Python |
| GPU acceleration | (closed source) |
| GUI framework | napari |
| RAW processing | rawpy |
| Image I/O | OpenImageIO |
| Numerical / spectral | NumPy, SciPy |

---

## Status

Active development. Closed source.

---

## Background

The simulation model draws on the theory of colour photography as described in Giorgianni & Madden's *Digital Color Management* and Hunt's *The Reproduction of Color*, and applies spectral primary decomposition techniques for scene reconstruction.
