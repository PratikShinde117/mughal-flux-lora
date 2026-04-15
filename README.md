# Flux-training-script

# 🎨 Mughal Style Image Generation using FLUX LoRA

## 📌 Overview

This project focuses on fine-tuning the **FLUX.1 model** using **LoRA (Low-Rank Adaptation)** to generate images in traditional Indian art styles such as **Mughal, Pahari/Kangra, and Ragamala paintings**.

The goal is to create a lightweight, efficient model capable of producing stylistically consistent outputs while preserving fine artistic details.

---

## 🚀 Key Features

* Fine-tuning FLUX.1-dev using LoRA
* Custom dataset of Indian miniature paintings
* Supports both **local training** and **Modal (cloud GPU) training**
* Config-driven training pipeline
* Sample image generation during training
* Optional Gradio UI for simplified training

---

## 🧠 Tech Stack

* Python 3.11
* PyTorch
* Hugging Face Diffusers
* FLUX.1 model (Black Forest Labs)
* Ostris AI Toolkit
* Modal (for cloud training)
* Gradio (optional UI)

---

## 📂 Project Structure

```
mughal-flux-lora/
│── README.md
│── requirements.txt
│── .gitignore
│
├── src/
│   ├── run.py
│   ├── run_modal.py
│   ├── version.py
│   └── flux_train_ui.py
│
├── config/
│   └── train_config.yaml
│
├── notebooks/
│   └── flux_training_pipeline.ipynb
│
├── sample_generated_images/
│   ├── sample1.png
│   ├── sample2.png
│   └── ...
```

---

## 📊 Dataset

The dataset consists of curated images from:

* Mughal paintings
* Pahari / Kangra style
* Ragamala paintings

> ⚠️ Dataset is not included due to size constraints.

---

## 🏋️ Training

### 🔹 Local Training

```bash
python src/run.py config/train_config.yaml
```

### 🔹 Modal (Cloud GPU Training)

```bash
modal run src/run_modal.py --config-file-list-str=config/train_config.yaml
```

> ⚠️ Update local paths in `run_modal.py` before running.

---

## ⚙️ Configuration

Training is controlled via YAML config:

* LoRA rank and alpha
* Learning rate
* Batch size
* Dataset path
* Sampling prompts

Example:

```yaml
train:
  steps: 2000
  lr: 1e-4
network:
  linear: 16
```

---

## 🖼️ Results

Sample outputs are available in the `samples/` directory.

The model successfully learns:

* Fine brushwork patterns
* Traditional color palettes
* Cultural composition styles

---


## 🔧 Setup Instructions

### 1. Clone this repository

```bash
git clone https://github.com/PratikShinde117/Flux-training-script
cd mughal-flux-lora
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Install AI Toolkit (required)

```bash
git clone https://github.com/ostris/ai-toolkit
cd ai-toolkit
pip install -r requirements_base.txt
```

---

## 🧪 Notebook

The `notebooks/flux_training_pipeline.ipynb` contains:

* Data preprocessing
* Training experiments
* Evaluation workflow

---

## ⚠️ Notes

* Ensure GPU availability for training
* Update dataset paths in config before running
* Large files (dataset, checkpoints) are excluded from repo

---

## 📌 Future Improvements

* Better prompt conditioning
* Higher resolution training
* Style mixing experiments
* Deployment as API

---

## 👤 Author

Pratik Shinde

---

## ⭐ Acknowledgements

* Black Forest Labs (FLUX)
* Ostris AI Toolkit
* Hugging Face Ecosystem

