# Generative Semantic Mesh Relaying for Disaster-Resilient Communication Beyond Cellular Networks

This repository contains notebooks, figures, datasets, and experimental outputs supporting the paper **"Generative Semantic Mesh Relaying for Disaster-Resilient Communication Beyond Cellular Networks."**

The project studies a **Generative Semantic Mesh (GSM)** architecture for disaster-resilient communication beyond cellular networks. GSM replaces raw emergency multimedia transmission with compact semantic descriptors, encrypted device-to-device relay, and generative reconstruction at the destination.

## Project Overview

Large-scale disasters can disable cellular infrastructure exactly when communities need evacuation guidance, shelter information, public-warning delivery, and triage support. Traditional device-to-device relay approaches can provide infrastructure independence, but raw multimedia payloads are difficult to forward efficiently through multi-hop relay chains.

GSM addresses this problem through a three-stage pipeline:

1. **Semantic Encoding**
   Disaster-relevant media is converted into compact semantic descriptors.

2. **Encrypted D2D Relay**
   The semantic descriptors are encrypted and forwarded through device-to-device relay nodes.

3. **Generative Reconstruction**
   The destination device reconstructs a semantically equivalent artifact from the received descriptor.

## Repository Contents

```text
.
├── README.md
├── .gitignore
├── 01_d2d_mesh_simulation.ipynb
├── fig_energy_overhead.svg
├── fig_network_topology.svg
├── fig_network_topology_optimized.svg
├── fig_pdr_latency.svg
├── fig_pdr_latency_optimized.svg
│
└── semantic_reconstruction/
    ├── .gitignore
    ├── D2D_Semantic_Transmission.ipynb
    ├── Pictures/
    ├── outputs/
    │   ├── captions.csv
    │   ├── results.csv
    │   ├── significance_tests.csv
    │   ├── summary.json
    │   ├── figures/
    │   └── tables/
    └── results.csv
```

## Notebooks

### 1. D2D Mesh Simulation

**File:** `01_d2d_mesh_simulation.ipynb`

This notebook supports the relay scalability component of the GSM paper. It simulates device-to-device communication behavior in a disaster-zone mesh and generates visual outputs related to network topology, packet delivery, latency, and energy-overhead behavior.

Main outputs include:

* Simulated D2D network topology
* Packet delivery and latency visualizations
* Energy-overhead analysis
* Optimized SVG figures for paper use

### 2. Semantic Reconstruction Evaluation

**File:** `semantic_reconstruction/D2D_Semantic_Transmission.ipynb`

This notebook supports the semantic reconstruction evaluation part of the paper. It evaluates disaster-relevant image reconstruction using multiple semantic reconstruction pipelines and stores the related data, figures, tables, and summary outputs.

Main contents include:

* `Pictures/` — image dataset used in the reconstruction evaluation
* `outputs/captions.csv` — image captions and semantic descriptions
* `outputs/results.csv` — reconstruction metric outputs
* `outputs/significance_tests.csv` — statistical comparison outputs
* `outputs/summary.json` — aggregate metric summary
* `outputs/figures/` — generated evaluation figures
* `outputs/tables/` — LaTeX tables used for reporting

## Evaluation Components

The repository supports two main experimental components from the paper:

### D2D Relay Simulation

This part evaluates the relay behavior of semantic descriptors in a simulated device-to-device mesh. It focuses on how packet-loss rate affects delivery probability, semantic throughput, latency, and energy-related behavior.

### Semantic Reconstruction Evaluation

This part evaluates the quality and safety of reconstructed disaster-relevant images. The evaluation compares multiple reconstruction pipelines using metrics such as:

* SSIM
* PSNR
* CLIP-I
* CMSC
* LPIPS
* Object Hallucination Rate

## Key Findings

The paper reports that no single reconstruction pipeline dominates all evaluation metrics. Different pipelines are preferable for different safety and quality priorities:

* **LLaVA+FLUX** achieved the strongest semantic alignment.
* **LLaVA+SDXL** achieved the lowest object hallucination rate.
* **LLaVA+ControlNet** achieved the strongest structural and perceptual preservation.

The relay simulation also demonstrates the potential benefit of replacing raw multimedia files with compact semantic descriptors for disaster communication under constrained network conditions.

## How to Run

Clone the repository:

```bash
git clone https://github.com/Apanoub-Benyamen/Generative-Semantic-Mesh-Relaying-for-Disaster-Resilient-Communication-Beyond-Cellular-Networks.git
```

Open the repository folder:

```bash
cd Generative-Semantic-Mesh-Relaying-for-Disaster-Resilient-Communication-Beyond-Cellular-Networks
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it:

```bash
# Windows PowerShell
.venv\Scripts\Activate.ps1
```

or:

```bash
# Git Bash
source .venv/Scripts/activate
```

Install the required packages according to the notebook requirements. Common packages include:

```bash
pip install numpy pandas matplotlib seaborn networkx scipy scikit-learn jupyter
```

Then open Jupyter Notebook or VS Code and run the notebooks.

## Notes

Virtual environment folders are excluded using `.gitignore` and are not uploaded to GitHub.

The image dataset in `semantic_reconstruction/Pictures/` is included because it is part of the reconstruction evaluation workflow.

## Research Status

This repository is intended for academic research and reproducibility. GSM is a research architecture and is not a deployment-ready emergency communication system. Larger outdoor mobility trials, real device battery measurements, metadata protection, and automated critical-field validation remain future work.

## Authors

* Abanoub Benyamin Yacoub Ghaly
* Adel Ehab Adel Mohamed
* Ebtehal Tamer Elshahhat

School of Management, Universiti Sains Malaysia, Penang, Malaysia

## Disclaimer

This repository is for academic research purposes only. The GSM architecture is a proposed research framework and should not be interpreted as a certified emergency communication system.
