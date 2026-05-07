# VAFMNet

This repository is a lightweight super-resolution training and testing framework built upon [BasicSR](https://github.com/XPixelGroup/BasicSR).

It is designed for convenient development, training, and evaluation of custom image super-resolution models.

---

# Project Structure

```text
├── archs/                  # Super-resolution model architectures
├── options/                # YAML configuration files
│   ├── train/
│   └── test/
├── train.py                # Training script
├── test.py                 # Testing script
├── datasets/
├── models/
├── utils/
└── README.md
```

---

# Environment Setup

## Clone Repository

```bash
git clone https://github.com/MinGTu1/VAFMNet.git
cd VAFMNet
```

## Create Environment

```bash
conda create -n basicsr python=3.10
conda activate basicsr
```

## Install Dependencies

```bash
pip install torch torchvision
pip install -r requirements.txt
```

Or install BasicSR manually:

```bash
pip install basicsr
```

---

# Dataset Preparation

Organize datasets as follows:

```text
datasets/
├── train/
│   ├── HR/
│   └── LR/
|          X2/
|          X3/
|          X4/
├── val/
│   ├── HR/
│   └── LR/
|          X2/
|          X3/
|          X4/
```

Dataset paths can be modified in YAML files under `options/`.

---

# Training

Training configuration files are stored in:

```text
options/train/
```

Run training with:

```bash
python train.py -opt options/train/VAFMNet_DIV2K_100w_x2SR.yml
```

Example:

```bash
python train.py -opt options/train/VAFMNet_DIV2K_100w_x2SR.yml
```

---

# Testing

Testing configuration files are stored in:

```text
options/test/
```

Run testing with:

```bash
python test.py -opt options/test/benchmark_VAFMN_x2.yml
```

Example:

```bash
python test.py -opt options/test/benchmark_VAFMN_x2.yml
```

---

# Custom Model

All custom super-resolution architectures should be placed in:

```text
archs/
```

Example:

```text
archs/
├── VAFMNet_arch.py
```

After adding a new architecture, register it properly so that it can be called by the YAML configuration.

---

# YAML Configuration

All experiment settings are managed through YAML files, including:

- Network structure
- Dataset paths
- Training hyperparameters
- Optimizer settings
- Loss functions
- Validation settings

---

# Results

Training logs, checkpoints, and visual results are automatically saved during training/testing.

Typical outputs include:

```text
experiments/
results/
```

---

# Acknowledgements

This project is built upon the excellent framework:

- [BasicSR](https://github.com/XPixelGroup/BasicSR)

---

# License

This project is released under the MIT License.
