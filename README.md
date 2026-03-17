# WOUND_CHU - Public Extract

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC_BY--NC_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

## Overview

This repository is a **public extract of the WOUND_CHU dataset**, the first clinical
wound tissue segmentation dataset collected in sub-Saharan Africa.

The **full dataset** comprises 788 annotated images from 101 wounds with longitudinal
follow-up (up to 35 visits per wound), collected at **CHU Tambohobe, Fianarantsoa, Madagascar**.

This public extract provides **101 image/mask pairs (one per wound, median visit)**,
covering all 14 wound profiles and all 5 tissue annotation classes.

---

## Repository Structure

```
WOUND_CHU_PUBLIC/
+-- README.md
+-- LICENSE.md
+-- metadata.csv               <- per-image metadata + SegFormer-B2 Dice scores
+-- images/                    <- 101 wound photographs (.jpg)
+-- masks/                     <- 101 annotation masks (.png, pixel values 0-4)
+-- notebooks/
    +-- create_public_extract.ipynb
```

---

## Tissue Classes (mask pixel values)

| Value | Class | Clinical description |
|-------|-------|---------------------|
| 0 | Background | Non-wound region |
| 1 | Necrotic | Dead tissue (black / dark brown) |
| 2 | Atone | Slough / fibrin (yellow-beige) |
| 3 | Granulation | Vascularized budding tissue (bright red) |
| 4 | Epithelial | Nascent re-epithelialization (pink) |

---

## Image Selection Criteria

- **1 image per wound** (101 wounds, 101 images)
- **Median visit** per wound: avoids blurry admission images (first visit) and
  fully healed images (last visit); represents the active wound phase
- All **14 wound profiles** covered (dominant tissue x number of classes present)
- All **5 tissue classes** represented across the extract

---

## metadata.csv columns

| Column | Description |
|--------|-------------|
| `Image_ID` | Filename stem (e.g. `004_000-10-_jpg`) |
| `Wound_ID` | Anonymous wound identifier (integer) |
| `Wound_Profile` | Dominant tissue + class count (e.g. `Atone_4`) |
| `Fold` | Cross-validation fold (1-5) |
| `Global_Dice` | SegFormer-B2 Dice score |
| `Global_IoU` | SegFormer-B2 IoU score |
| `Dice_*` | Per-class Dice (Background/Necrotic/Atone/Granulation/Epithelial) |
| `has_*` | Binary flag: tissue class present in mask (0/1) |

---

## Access to Full Dataset

The complete dataset (788 images, longitudinal follow-up) is available to academic
researchers upon motivated request, subject to a **Data Sharing Agreement** guaranteeing:
- Patient anonymity
- Exclusive research use
- Compliance with applicable ethical regulations

**Request access:** [EMAIL_AUTEUR]

---

## Citation

```bibtex
@article{WOUND_CHU_2025,
  title   = {Transformer-Based Architectures Outperform CNNs for Multi-Class
             Wound Tissue Segmentation: A 16-Model Benchmark on a Novel
             African Clinical Dataset},
  author  = {[AUTEURS]},
  journal = {[JOURNAL]},
  year    = {2025},
  doi     = {[DOI]}
}
```

---

## Ethics and Privacy

- Ethics committee approval: CHU Tambohobe, Fianarantsoa, Madagascar
- Informed consent obtained from all patients
- Images systematically anonymized (no identifying information in filenames or metadata)
- Faces and identifying body parts excluded from image frame

---

## License

[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) --
free for academic/research use, **not for commercial purposes**.
