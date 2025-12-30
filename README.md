# GNFM
Release of the official implementation of GNFM and the Reflective Surgical Instrument Dataset (RSID)

# GNFM: Generalizable NeRF with View-Aware Feature Modulation  
### Reflective Surgical Instrument Rendering toward Robot-Assisted Surgery

📄 [Paper] | 📊 [Dataset (RSID)] | 💻 Code | 🎥 Video (coming soon)

![teaser](assets/teaser.png)

---

## Overview

Accurate 3D reconstruction and novel view synthesis of **small, highly reflective surgical instruments**
are critical for robust perception in robot-assisted surgery.
However, most existing generalizable NeRF methods are primarily validated on
**diffuse objects or large-scale scenes**, and often struggle with
fine-grained geometry and strong view-dependent reflections.

We propose **GNFM**, a **generalizable Neural Radiance Field (NeRF) framework**
tailored for **reflective surgical instruments**.
GNFM enables cross-object generalization **without per-object finetuning**
while preserving thin structures and view-dependent appearance.

Our main contributions are:

- **JMHE (Joint Multiresolution Hash Encoder)** for unified spatial–directional encoding  
- **V-FiLM (View-Conditional Feature-wise Linear Modulation)** for view-aware radiance modeling  
- **RSID Dataset**, a benchmark for reflective surgical instrument rendering

---

## Method

![pipeline](assets/pipeline.png)

GNFM follows a generalizable NeRF paradigm and consists of:
1. A shared geometry–appearance backbone across multiple objects  
2. JMHE for joint spatial and directional feature encoding  
3. V-FiLM for view-conditioned feature modulation before color prediction  

This design allows GNFM to better model **thin edges, fine geometry,
and strong specular reflections**, which are common in surgical instruments.

---

## Reflective Surgical Instrument Dataset (RSID)

RSID is a synthetic dataset designed for evaluating generalizable NeRF models
on **small-scale, highly reflective surgical instruments**.

**Dataset statistics:**

- 8 categories of surgical instruments  
- 2,400 rendered images  
- Resolution: 800 × 800  
- Camera radius: 0.3–0.5 m  
- Official train / validation / test splits  

| Instrument | Train | Val | Test |
|-----------|-------|-----|------|
| Scalpel   | 100   | 100 | 100  |
| Forceps  | 100   | 100 | 100  |
| Tweezers | 100   | 100 | 100  |
| ...       | ...   | ... | ...  |

📊 **Dataset Download:** [RSID Dataset Link]

---

## Installation

We recommend using **Conda** to reproduce the experimental environment.

```bash
conda env create -f environment.yml
conda activate gnfm
