<div align="center">

# 🦴 Bone Layer Extraction from Chest X-Rays
### Deep Learning-Based Bone Structure Enhancement using U-Net + Perceptual Loss

*A deep learning pipeline to predict and isolate bone structures from chest X-ray images using synthetic CT-DRR data*

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/latashasingh43-commits/Deep-Learning-Based-Bone-Structure-Enhancement-in-Chest-X-Ray-Images/blob/main/bone-drr-unet.ipynb)
[![Open in NBViewer](https://img.shields.io/badge/Open-NBViewer-orange?logo=jupyter)](https://nbviewer.org/github/latashasingh43-commits/Deep-Learning-Based-Bone-Structure-Enhancement-in-Chest-X-Ray-Images/blob/main/bone-drr-unet.ipynb)
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?logo=tensorflow&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

</div>

---

## 📖 About the Project

Chest X-rays contain overlapping anatomical structures — soft tissue, organs, and bone — making it difficult to isolate skeletal features for analysis. This project tackles that problem by training a **U-Net model** to predict the bone layer directly from X-ray images, using **synthetically generated Digitally Reconstructed Radiographs (DRR)** as paired ground truth.

By learning to enhance and separate bone structures, this approach can support downstream tasks such as **fracture detection, bone density analysis, and orthopedic diagnostics** — areas where isolating skeletal detail from soft tissue noise is often the first and hardest step.

**Dataset:** [Digitally Reconstructed Radiographs (DRR) - Bones](https://www.kaggle.com/raddar/digitally-reconstructed-radiographs-drr-bones)

---

## 🏗️ Model Architecture

| Component | Details |
|---|---|
| 🧠 Architecture | U-Net (Encoder-Decoder with skip connections) |
| 🎯 Task | Image-to-Image Translation (Bone Layer Prediction) |
| 📉 Loss Function | Perceptual Loss (VGG19-based) |
| ⚡ Framework | TensorFlow / Keras |
| 📐 Training | 200 epochs with learning rate scheduling |

The model is trained using a **VGG19-based perceptual loss**, which compares high-level feature representations rather than raw pixel values — helping the network produce sharper, more anatomically realistic bone predictions instead of blurry pixel-averaged outputs.

### Pipeline Overview

```
Chest X-Ray Input
       │
       ▼
┌─────────────────┐
│   U-Net Encoder  │  ── downsampling, feature extraction
└─────────────────┘
       │
       ▼
┌─────────────────┐
│   U-Net Decoder  │  ── upsampling, skip connections
└─────────────────┘
       │
       ▼
 Predicted Bone Layer
       │
       ▼
┌─────────────────────┐
│ VGG19 Perceptual Loss │ ── compares features vs. ground truth DRR
└─────────────────────┘
```

---

## ⚙️ Tech Stack

`Python` &nbsp;`TensorFlow` &nbsp;`Keras` &nbsp;`VGG19` &nbsp;`NumPy` &nbsp;`OpenCV` &nbsp;`Matplotlib`

---

## ✨ Key Features

- 🔧 **End-to-end pipeline** — from raw DRR dataset extraction to a trained model
- 🧬 **U-Net architecture** for pixel-wise bone structure prediction
- 📈 **Perceptual loss (VGG19)** for visually realistic, structure-aware outputs
- 🖼️ **Visual comparisons** of predicted bone layers vs. ground truth DRRs
- 📊 **Quantitative evaluation** using SSIM and PSNR metrics
- 🚀 Reproducible training pipeline with checkpointing and learning-rate scheduling

---

## 🖼️ Sample Results

<div align="center">

| Input X-Ray | Predicted Bone Layer | Ground Truth DRR |
|:---:|:---:|:---:|
| *add image* | *add image* | *add image* |

</div>

> 💡 Add sample output images from your notebook here (drag-and-drop into a `results/` folder via GitHub's "Add file → Upload files", then reference them like `![](results/sample1.png)`).

---

## 📊 Results

Final evaluation on the test set:

| Metric | Score | What it means |
|---|---|---|
| 🎯 Average SSIM | **0.3634** | Structural similarity between predicted and ground-truth bone layers |
| 📡 Average PSNR | **19.96 dB** | Pixel-level reconstruction quality |


---

## 🚀 Getting Started

1. Click the **Open in Colab** badge above
2. Mount your Google Drive and update the dataset path
3. Run all cells sequentially to extract data, train the model, and evaluate results
4. View predicted bone layer outputs in the visualization section

---

## 🔮 Future Roadmap

- [ ] Improve SSIM/PSNR with deeper architectures or hybrid loss functions
- [ ] Fine-tune on real chest X-ray datasets for clinical applicability
- [ ] Experiment with GAN-based refinement for sharper outputs
- [ ] Deploy as a simple web demo for visualization

---

## 👩‍💻 Author

**Latasha Singh**

[![GitHub](https://img.shields.io/badge/GitHub-181717?logo=github&logoColor=white)](https://github.com/latashasingh43-commits)

---

<div align="center">

⭐ **If you found this project useful, consider giving it a star!** ⭐

</div>
