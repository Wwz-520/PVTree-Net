## Overview

PVTree-Net is a 3D medical image segmentation framework for the unified delineation of the portal vein (PV) and portal vein tumor thrombus (PVTT) in portal venous phase CT.
The project is built on nnU-Net v2 and combines:
a 3D residual encoder for stable multiscale feature extraction;
pyramid split attention in high-level skip connections;
FedProx-based federated fine-tuning using NVIDIA FLARE;
refined portal-vein annotations for public CT datasets.

## Introduction
PV and PVTT are treated as a single foreground class. This design prioritizes preservation of the complete portal venous tree and thrombus-related vascular continuity.

The main components of PVTree-Net include:

- A 3D residual encoder for robust multiscale vascular feature extraction.
- Pyramid split attention in high-level skip connections.
- Multiscale convolutional kernels for vessels with large diameter variations.
- FedProx-based federated fine-tuning using NVIDIA FLARE.
- Revised and publicly released portal-vein annotations derived from public abdominal CT datasets.

This repository provides:

- The source code of the PVTree-Net architecture.
- The implementation of FedProx-based federated fine-tuning.
- Revised portal-vein annotations for public CT datasets.
- Example annotation masks and related documentation.

## Dataset

### Private multi-center dataset

The private dataset used in this study contains **536 portal venous phase CT cases** collected from two medical centers:

- Center A: 326 cases.
- Center B: 210 cases.
- PVTT-positive cases: 332.
- Non-PVTT cases: 204.

The private clinical dataset is not publicly released because of patient privacy and institutional data-protection requirements.

### Public datasets

The public datasets involved in this project include:

- **Medical Segmentation Decathlon Task08: HepaticVessel**
- **3D-IRCADb-01**

The original CT images should be downloaded from the official websites of the corresponding datasets.

The revised annotation masks created in this project are provided in this repository.

### Revised MSD Task08 annotations

The MSD Task08 dataset contains 303 labeled training CT volumes. Its original vascular annotations may contain both portal-vein and hepatic-vein structures.

We manually reviewed and refined these annotations to obtain portal-vein masks with a more consistent anatomical definition.

The main modifications include:

- Separating the portal vein from the hepatic veins.
- Removing hepatic-vein regions incorrectly connected to the portal-vein mask.
- Correcting mislabeled or anatomically inconsistent vascular regions.
- Repairing interrupted portal-vein branches.
- Supplementing visible distal intrahepatic portal-vein branches.
- Removing isolated noise and implausible disconnected components.
- Standardizing the annotation scope across cases.

For external evaluation in our study, 61 thin-slice CT volumes with slice thickness below 2 mm were used.

### Revised 3D-IRCADb-01 annotations

The 3D-IRCADb-01 dataset contains 20 abdominal CT volumes.

We further refined the public vascular annotations according to the portal-vein segmentation target used in this study.

The main modifications include:

- Retaining the portal venous tree associated with the liver.
- Removing the splenic vein.
- Removing the superior mesenteric vein outside the target definition.
- Correcting discontinuous or missing portal-vein branches.
- Refining distal intrahepatic portal-vein structures.
- Removing non-target vessels, isolated regions, and annotation noise.

### Access

The revised masks are available in:

```text
PVTree-Net/
├── data/
│   ├── PV_01.nii.gz
│   ├── ...
│   ├── PV_20.nii.gz
│   ├── labels.zip
│   └── README.md
└── reannotated.zip
```

- `data/` contains revised portal-vein annotations and example resources associated with 3D-IRCADb-01.
- `reannotated.zip` contains the revised public-dataset annotation package.

### Important data-use statement

This repository releases the **revised segmentation masks**, not the ownership of the original CT images.

Users must:

- Download the original CT images from the official dataset providers.
- Follow the licenses and terms of the original datasets.
- Match the revised masks with the corresponding original cases.
- Cite both the original datasets and the PVTree-Net project when using these annotations.
