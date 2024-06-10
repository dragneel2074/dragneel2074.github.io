---
title: "Nepali Text Summarization Fine-Tuning"
excerpt: "Fine-tuning the Phi model for Nepali text summarization using Unsloth library"
collection: portfolio
---

I developed a Nepali Text Summarization model by fine-tuning the Phi model using the Unsloth library.

**Key Steps:**
1. **Environment Setup:** Installed necessary packages, including Unsloth and Xformers.<br/>
2. **Model Selection:** Utilized the [unsloth/Phi-3-mini-4k-instruct](https://huggingface.co/unsloth/Phi-3-mini-4k-instruct) model with 4-bit quantization to reduce memory usage.<br/>
3. **Parameter Configuration:** Set parameters for fine-tuning:
   - `max_seq_length`: 2048
   - `dtype`: Automatically detected (Float16 for Tesla T4, V100, Bfloat16 for Ampere+)
   - `load_in_4bit`: True<br/>

4. **Dataset:** Utilized the [Nepali Summarization Dataset](https://huggingface.co/datasets/sanjeev-bhandari01/nepali-summarization-dataset) from Hugging Face.<br/>
5. **Prompt Template:** Used a custom Alpaca prompt template for formatting the input texts for summarization.<br/>

**Fine-Tuning Techniques:**
- **LoRA Adapters:** Applied Low-Rank Adaptation (LoRA) to update 1-10% of the model parameters.
- **Training Parameters:**
  - `r`: 16
  - `target_modules`: ["q_proj", "k_proj", "v_proj", "o_proj", "gate_proj", "up_proj", "down_proj"]
  - `lora_alpha`: 16
  - `lora_dropout`: 0
  - `bias`: "none"
  - `use_gradient_checkpointing`: "unsloth" for memory optimization
  - `random_state`: 3407
  - `use_rslora`: False
  - `loftq_config`: None

**Training Results:**
- **Metrics:**
  - `train_runtime`: 744.6389 seconds
  - `train_samples_per_second`: 1.074
  - `train_steps_per_second`: 0.134
  - `total_flos`: 1.018262453428224e+16
  - `train_loss`: 1.2545
  - `epoch`: 0.0028


**Live Project:** [Nepali Text Summarization](https://huggingface.co/Dragneel/Phi-3-mini-Nepali-Text-Summarization-f16)

