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
