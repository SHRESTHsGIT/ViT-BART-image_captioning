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
  
## 📈 Results

After training for 5 epochs with beam search (`num_beams=6`) and `max_length=128`, the model performance on the validation set is summarized below:

| Metric    | Score     |
|-----------|-----------|
| ROUGE-1   | 0.309     |
| ROUGE-2   | 0.010     |
| ROUGE-L   | 0.265     |
| Val Loss  | 3.30      |

- The model successfully learned to generate relevant image captions using ViT-BART.
- Loss steadily decreased across epochs showing good convergence.
- ROUGE metrics indicate moderate overlap with reference captions, typical for image captioning tasks.
  
## 📁 Dataset Structure

The project uses the Flickr30k dataset for training and evaluation.

Your dataset folder should be organized as follows:
flickr30k/
    ├── Images/
    │   ├── 1000092795.jpg
    │   ├── 1001465946.jpg
    │   └── ...
    └── captions.csv
## 🏗️ Setup

### Kaggle
The project is built and tested on [Kaggle Notebooks](https://www.kaggle.com/code). You can clone the repo and upload both notebooks to your Kaggle account for seamless execution.



### Local Setup
To run this locally (GPU required):

```bash
git clone https://github.com/your-username/vit-bart-image-captioning.git
cd vit-bart-image-captioning
pip install -r requirements.txt



