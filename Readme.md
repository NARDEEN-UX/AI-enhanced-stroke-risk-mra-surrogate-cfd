# AI-Enhanced Stroke Risk Assessment Using MRA & Surrogate CFD

[![Python](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red.svg)](https://pytorch.org/)
[![Next.js](https://img.shields.io/badge/Next.js-16.0-black.svg)](https://nextjs.org/)
[![React Three Fiber](https://img.shields.io/badge/R3F-3D%20Rendering-orange.svg)](https://docs.pmnd.rs/react-three-fiber/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 🎯 Overview

The **AI-Enhanced Stroke Risk Assessment** project aims to predict stroke risk using brain Magnetic Resonance Angiography (MRA) by integrating aneurysm detection, stenosis quantification, and surrogate Computational Fluid Dynamics (CFD) modeling for real-time hemodynamic analysis (evaluating factors like TAWSS and OSI).

This repository is split into two primary components:
1. **Deep Learning Model Pipeline**: A robust pipeline focusing on aneurysm classification from MRA sequences using Vision Transformers.
2. **Interactive Web Application (No-Clot-Zone)**: A modern, real-time interactive frontend designed to visualize risk factors and render 3D vascular representations based on surrogate CFD parameters.

---

## 🏗️ Project Structure

```text
.
├── Aneurysm Classification from different modalities Using deeplearning/
│   ├── notebooks/       # Jupyter notebooks for model training and EDA
│   ├── Plots/           # Performance evaluation visualizations (ROC, Confusion Matrix, etc.)
│   ├── predictions/     # Sample predictions output
│   └── README.md        # Detailed documentation for the DL pipeline
├── No-Clot-Zone/
│   ├── app/             # Next.js App Router containing pages and API endpoints
│   ├── components/      # React components (Radix UI, 3D elements, layout)
│   ├── hooks/           # Custom React hooks
│   ├── lib/             # Utility functions
│   └── package.json     # Web app dependencies and scripts
└── README.md            # Root documentation (You are here)
```

---

## 🌟 Key Features

- **Aneurysm Detection via ViT**: Utilizes a fine-tuned Swin Transformer Tiny architecture to perform binary classification (Aneurysm Present vs. Not Present) using MRA sequences, demonstrating a strong performance with an AUC of 0.9132 on final test datasets.
- **Surrogate CFD Modeling**: Approximates complex Computational Fluid Dynamics metrics like Time-Averaged Wall Shear Stress (TAWSS) and Oscillatory Shear Index (OSI) using AI to provide near real-time hemodynamic feedback.
- **3D Interactive Visualization**: The `No-Clot-Zone` web application uses React Three Fiber (`@react-three/fiber`, `@react-three/drei`) to render intuitive 3D models of blood vessels directly in the browser, helping medical practitioners analyze regions of interest dynamically.
- **Modern Tech Stack Dashboard**: Incorporates modern web tools (Next.js 16, TailwindCSS, Radix UI primitives, Recharts) for an elegant, user-friendly, and responsive interface tailored for clinical review workflows.

---

## 💻 Technology Stack

### Deep Learning & AI
- **Frameworks**: PyTorch, Timm (PyTorch Image Models)
- **Data Processing**: Pydicom, OpenCV, Pandas, NumPy
- **Machine Learning Tools**: Scikit-Learn

### Web Application (No-Clot-Zone)
- **Frontend Framework**: Next.js (React 19)
- **Styling**: Tailwind CSS v4, PostCSS, Radix UI Primitives, Lucide-React
- **3D Rendering**: Three.js, React Three Fiber, React Three Drei
- **Data Visualization**: Recharts

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed on your system:
- **Python 3.11+**
- **Node.js 22+**
- **Git**
- **CUDA-compatible GPU** (Highly Recommended for Model Training)

### 1. Setup the Deep Learning Pipeline

Navigate to the model directory and install the necessary dependencies:

```bash
cd "Aneurysm Classification from different modalities Using deeplearning"
pip install torch torchvision torchaudio
pip install timm pydicom opencv-python pandas numpy scikit-learn matplotlib seaborn joblib tqdm
```
*Note: For complete details regarding the dataset (RSNA Intracranial Aneurysm Detection) and execution instructions, refer to the [Deep Learning Pipeline README](./Aneurysm%20Classification%20from%20different%20modalities%20Using%20deeplearning/README.md).*

### 2. Setup the Web Application

Navigate to the frontend directory to set up the dashboard:

```bash
cd No-Clot-Zone
npm install
# Or if you use pnpm
pnpm install
```

Start the development server:

```bash
npm run dev
# Or with pnpm
pnpm dev
```
Open [http://localhost:3000](http://localhost:3000) with your browser to see the interactive 3D dashboard.

---

## 📈 Results & Performance

The core classification model achieved strong metrics on the test set:
- **Accuracy**: 84.84%
- **Sensitivity (Recall)**: 89.3%
- **AUC Score**: 0.9132
- **F1 Score**: 0.8942

The web frontend leverages these insights to render risk zones visually, providing an interactive diagnostic aid for medical professionals.

---

---

## 📄 License

This project is licensed under the MIT License - see the `LICENSE` file for details.

---

**Disclaimer**: This project and its corresponding AI models are strictly for research and educational purposes. They are not intended to replace professional medical advice, diagnosis, or treatment. Always consult certified medical professionals for clinical decisions.
