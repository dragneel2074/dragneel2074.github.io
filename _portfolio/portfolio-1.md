---
title: "Nepali Text Summarization with MBart"
excerpt: "Fine-tuning the MBart model for Nepali text summarization using the Transformers library <br/><img src='/images/mbart_summarization.png'>"
collection: portfolio
---

I developed a Nepali Text Summarization model by fine-tuning the MBart model using the Transformers library.

**Key Steps:**
1. **Environment Setup:** Installed necessary packages, including Accelerate and Transformers.<br/>
2. **Model and Tokenizer:** Utilized the [facebook/mbart-large-cc25](https://huggingface.co/facebook/mbart-large-cc25) model with the MBartTokenizer.<br/>
3. **Dataset:** Loaded the [Nepali Summarization Dataset](https://huggingface.co/datasets/sanjeev-bhandari01/nepali-summarization-dataset) from Hugging Face.<br/>
4. **Target Language Configuration:** Set both source and target language codes to Nepali (ne_NP).<br/>

**Preprocessing:**
- **Input Tokenization:** Tokenized the input articles to a maximum length of 1024 tokens.
- **Target Tokenization:** Tokenized the target titles to a maximum length of 128 tokens.
- **Data Mapping:** Applied the preprocessing function to the dataset.

**Training Configuration:**
- **TrainingArguments:**
  - `output_dir`: './results'
  - `evaluation_strategy`: 'epoch'
  - `learning_rate`: 3e-5
  - `per_device_train_batch_size`: 2
  - `per_device_eval_batch_size`: 2
  - `num_train_epochs`: 3
  - `weight_decay`: 0.01
  - `logging_dir`: './logs'
  - `logging_steps`: 10

**Evaluation Metric:**
- **Rouge Metric:** Utilized Rouge for evaluation, focusing on the `rouge2` score for precision, recall, and F-measure.

**Live Project:** [Nepali Text Summarization with MBart](https://huggingface.co/Dragneel/Nepali-Text-Summarizer-mBart)

**Image:**
<img src='/images/mbart_summarization.png'>
