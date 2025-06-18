# ViT-BART Image Captioning on Flickr30k

This repository contains a complete image captioning pipeline using a Vision Transformer (ViT) encoder and a BART decoder. The project was developed and trained on Kaggle using the Flickr30k dataset.

## 🔍 Overview

- **Model Architecture:** VisionEncoderDecoderModel combining `ViT-base` (Google) as encoder and `BART-base` (Facebook) as decoder.
- **Dataset:** [Flickr30k](https://shannon.cs.illinois.edu/DenotationGraph/) – a dataset of 31,000 images with five captions per image.
- **Goal:** Generate accurate and fluent captions for given images.
- **Notebook Files:**
  - `vit-bart.ipynb`: Training pipeline
  - `testing-vit-bart.ipynb`: Inference and evaluation

## 🧠 Features

- Custom `collate_fn` and `Dataset` class for dynamic batching.
- Integrated `Seq2SeqTrainer` with evaluation using ROUGE metrics.
- Early stopping and model checkpointing based on validation loss.
- Configurable number of epochs, batch sizes, and beam search parameters.
- Gradient checkpointing enabled for memory efficiency.

## 🏗️ Setup

### Kaggle
The project is built and tested on [Kaggle Notebooks](https://www.kaggle.com/code). You can clone the repo and upload both notebooks to your Kaggle account for seamless execution.

### Local Setup
To run this locally (GPU required):

```bash
git clone https://github.com/your-username/vit-bart-image-captioning.git
cd vit-bart-image-captioning
pip install -r requirements.txt
