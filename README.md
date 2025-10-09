# 📰 News Topic Classification (Transfer Learning with RoBERTa)

This project demonstrates **transfer learning for text classification** using a pre-trained transformer model fine-tuned on a related news dataset.  
A model originally trained on the **AG News** dataset (4 tpic categories) is further fine-tuned on the **BBC News** dataset to classify articles into 5 topic categories.

---

## 🔍 Overview

Large language models like **RoBERTa** can capture general linguistic and domain-specific patterns.  
By reusing a model fine-tuned on a related dataset, we can achieve strong performance on a smaller, domain-specific dataset — a key idea in **transfer learning**.

This notebook fine-tunes:
- Base model: [`textattack/roberta-base-ag-news`](https://huggingface.co/textattack/roberta-base-ag-news)
- Target dataset: [`SetFit/bbc-news`](https://huggingface.co/datasets/SetFit/bbc-news)
---

## 🧠 Base Model

- **Model:** `textattack/roberta-base-ag-news`  
- **Task:** News topic classification (4 categories: *World, Sports, Business, Sci/Tech*)  
- **Architecture:** RoBERTa-base  
- **Training details:**
  - Epochs: 5  
  - Batch size: 16  
  - Learning rate: 5e-5  
  - Max sequence length: 128  
  - Loss: Cross-entropy  
- **Best eval accuracy:** 0.9469 (after 4 epochs)

---

## 📚 Target Dataset for Transfer Learning

- **Dataset:** `SetFit/bbc-news`  
- **Labels:** 5 classes — *Business, Entertainment, Politics, Sport, Tech*  
- **Samples:** 2,225 BBC news articles (2004–2005)  
- **Source:** BBC News website  
- **Repository:** [Hugging Face Dataset](https://huggingface.co/datasets/SetFit/bbc-news)

---

## ⚙️ Fine-tuning Setup

| Parameter | Value |
|------------|--------|
| Base model | `textattack/roberta-base-ag-news` |
| Dataset | `SetFit/bbc-news` |
| Epochs | 3 |
| Batch size | 8 |
| Learning rate | 4e-5 |

---

## 🏁 Training Results

| Parameter | Value |
|------------|--------|
| Train Loss | 0.275600 |
| Val Loss | 0.297721 |
| Accuracy | 0.907988 |
| F1 Score | 0.906632 |

---
## 🚀 Deployment

After training, the fine-tuned model is deployed via a **Gradio interface** for interactive inference.

### 🎥 App Preview
🎬 [Watch full demo (MP4)](https://huggingface.co/spaces/TetorisAce/news_classifier/blob/main/assets/app_demo.mp4)

### 🚀 Live Demo
Open the Interactive App on Hugging Face Spaces → [Live_demo](https://huggingface.co/spaces/TetorisAce/news_classifier)

#### ⚠️ Note on Hugging Face Spaces (Free Tier)
This Gradio demo is hosted on Hugging Face Spaces using the free tier, which automatically puts the app to sleep after 72 hours of inactivity.

---

## 🧾 References

[textattack/roberta-base-ag-news (Hugging Face)](https://huggingface.co/textattack/roberta-base-ag-news)

[SetFit/bbc-news dataset (Hugging Face)](https://huggingface.co/datasets/SetFit/bbc-news)
