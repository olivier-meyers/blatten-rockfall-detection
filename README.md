# Blatten rockfall detection

Few-shot deep learning for detecting small rockfalls in continuous seismic data from the source area of the 2025 Blatten collapse (Lötschental, Switzerland).

**Status: work in progress.** Code will be released upon publication. Paper in preparation at the Swiss Seismological Service (ETH Zürich).

## Problem

Large slope failures such as the May 2025 Blatten collapse are often preceded by increasing rockfall activity. Building a rockfall catalogue from continuous seismic data is hard for three reasons: labelled events are scarce, rockfall signals vary widely in shape, and they have to be separated from earthquakes, aircraft and other noise.

<p align="center"><img src="figures/signal_examples.png" width="760" alt="Waveforms and spectrograms of rockfalls, noise and an earthquake"></p>

*Rockfalls (green) next to the noise sources and earthquakes (grey, red) a detector has to reject.*

## Approach

- **Siamese CNN on spectrograms.** It learns an embedding in which rockfalls lie close together and away from noise, and is trained contrastively from a small set of hand-picked events.
- **Template-based detection.** Each window of continuous data is scored by its angular distance to a set of labelled rockfall templates, so new examples can be added without retraining.
- **Benchmarks.** Compared against embeddings from a pretrained seismic foundation model and a classical STA/LTA detector, on hand-labelled continuous data.

<p align="center"><img src="figures/snn_architecture.png" width="860" alt="Siamese network architecture"></p>

---
MSc thesis, ETH Zürich, supervised by Dario Jozinović and John Clinton
