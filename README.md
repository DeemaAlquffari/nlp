# nlp

<div dir="ltr" align="left">

# 🗣️ Arabic Dialect to MSA Translator

This project fine-tunes an Arabic pre-trained language model to convert Arabic **dialects** into **Modern Standard Arabic (MSA)** using **transformers** and **🤗 Hugging Face datasets**.

## 📌 Project Goal

Enable automatic and accurate translation of informal Arabic dialects (like Saudi, Egyptian, etc.) into formal Arabic (MSA), useful for:

- Arabic NLP preprocessing
- Chatbot normalization

## 🧠 Model Used

We started with the pre-trained model:
Murhaf/AraT5-MSAizer

Then fine-tuned it on the public dataset:
PRAli22/Arabic_dialects_to_MSA

The model is a **Seq2Seq transformer** from the AraT5 family, trained specifically on dialect-to-MSA pairs.

## 🛠️ Main Technologies

- Python
- 🤗 Transformers
- Datasets (Hugging Face)
- Gradio (for demo interface)
- Google Colab



📊 Evaluation Results
Metric	Before Fine-tuning	After Fine-tuning
BLEU	0.08	                0.20

