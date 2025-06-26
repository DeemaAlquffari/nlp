# nlp

<div dir="ltr" align="left">

# 🗣️ Arabic Dialect to MSA Translator

This project fine-tunes an Arabic pre-trained language model to convert Arabic **dialects** into **Modern Standard Arabic (MSA)** using **transformers** and **🤗 Hugging Face datasets**.

## 📌 Project Goal

Enable automatic and accurate translation of informal Arabic dialects (like Saudi, Egyptian, etc.) into formal Arabic (MSA), useful for:

- Arabic NLP preprocessing
- Chatbot normalization
- Educational tools

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

## ⚙️ How to Use

You can use the model by running the Gradio demo:

```python
from transformers import AutoTokenizer, AutoModelForSeq2SeqLM
import gradio as gr

tokenizer = AutoTokenizer.from_pretrained("path_to_model")
model = AutoModelForSeq2SeqLM.from_pretrained("path_to_model")

def translate(text):
    input_text = "translate dialect to MSA: " + text
    inputs = tokenizer(input_text, return_tensors="pt", truncation=True, padding=True)
    output = model.generate(**inputs, max_new_tokens=100)
    return tokenizer.decode(output[0], skip_special_tokens=True)

gr.Interface(fn=translate, inputs="text", outputs="text", title="Arabic Dialect to MSA").launch()

aluation Results
Metric	Before Fine-tuning	After Fine-tuning
BLEU	0.08	0.20


