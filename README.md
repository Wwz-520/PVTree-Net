**Overview**

PVTree-Net is a 3D medical image segmentation framework for the unified delineation of the portal vein (PV) and portal vein tumor thrombus (PVTT) in portal venous phase CT.
The project is built on nnU-Net v2 and combines:
a 3D residual encoder for stable multiscale feature extraction;
pyramid split attention in high-level skip connections;
FedProx-based federated fine-tuning using NVIDIA FLARE;
refined portal-vein annotations for public CT datasets.
PV and PVTT are treated as a single foreground class. This design prioritizes preservation of the complete portal venous tree and thrombus-related vascular continuity.
> \*\*Research use only.\*\* This repository is not a medical device and must not be used for clinical diagnosis or treatment decisions.
