# Deep_Learning_Assignment1
This repository contains the implementation and experimental analysis for the assignment:  “Stress-Testing of Convolutional Neural Networks”

---

# Stress-Testing of Convolutional Neural Networks (CNNs)

## Overview

The goal of this project is not only to achieve good classification accuracy, but to critically analyze CNN behavior through:

* Baseline training
* Failure case discovery
* Explainability analysis (Grad-CAM)
* Constrained model improvement
* Behavioral reflection

All experiments were implemented using **PyTorch** and executed on **Google Colab**.

---

## Dataset

**Dataset Used:** CIFAR-10

* 50,000 training images
* 10,000 test images
* 10 classes
* Image size: 32×32 RGB

Only the official train–test split was used.
No external data or pretrained weights were used.

---

## Model Architecture

**Baseline Model:** Custom SimpleCNN

* 3 Convolutional layers
* ReLU activations
* MaxPooling
* Fully Connected classifier
* CrossEntropyLoss
* Optimizer: Adam
* Random Seed: 42

All models were trained **from scratch**.

---

## Experiments Conducted

###  Baseline Training

* Training & validation loss curves
* Training & validation accuracy curves
* Final test accuracy evaluation

### Failure Case Discovery

* Identified high-confidence misclassifications
* Selected at least 3 distinct failure cases
* Analyzed prediction confidence and visual characteristics

### Explainability (Grad-CAM)

* Applied Grad-CAM on final convolution layer
* Visualized attention maps for failure cases
* Compared highlighted regions with human intuition

### Constrained Improvement

* Applied exactly one modification:

  **Data Augmentation (RandomCrop + RandomHorizontalFlip)**

* Retrained model from scratch

* Compared robustness and behavior with baseline

---

## Repository Structure

```
.
├── DL_assign1.ipynb          # Main Colab notebook
├── outputs/                  # Saved plots and Grad-CAM images
├── report.pdf                # Final submitted report
└── README.md                 # Project documentation
```

---

## How to Reproduce the Results

### Option 1: Run on Google Colab (Recommended)

1. Open Google Colab
2. Upload `M25MAC003_M25MAC007_M25MAC012_M23MA2010_DLassign1.ipynb`
3. Run all cells sequentially

Make sure runtime is set to:

* **Python 3**
* **GPU enabled** (Runtime → Change runtime type → GPU)

---

### Option 2: Run Locally 

#### Requirements

* Python 3.8+
* PyTorch
* torchvision
* matplotlib
* numpy

Install dependencies:

```bash
pip install torch torchvision matplotlib numpy
```

Then run:

```bash
jupyter notebook DL_assign1.ipynb
```

---

## Reproducibility

* Random seed fixed to: **42**
* No pretrained models used
* All experiments performed under identical conditions
* Same architecture used across all experiments

---

## Key Observations

* CNNs can produce high-confidence incorrect predictions.
* The model often relies on texture and global shape.
* Grad-CAM reveals background bias in some failure cases.
* Data augmentation improves robustness but does not eliminate all failure modes.

---

## Important Notes

* No external datasets were used.
* No pretrained weights were used.
* All figures in the report were generated using our own code.
* Implementation strictly uses **PyTorch**, as required.

---

## Group Members
Arjun Singh (M25MAC003)                           Vijay Kumar Prajapati (M23MA2010)
Rajesh Meena (M25MAC007)                        Smithi Sureshan (M25MAC012)



