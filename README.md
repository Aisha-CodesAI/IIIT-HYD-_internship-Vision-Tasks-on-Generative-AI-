# IIIT-HYD-_internship-Vision-Tasks-on-Generative-AI-
"Local Generative AI with ComfyUI – exploring Stable Diffusion workflows, prompt engineering, and local AI model deployment. Developed during an internship at IIIT Hyderabad."

# Local Generative AI with ComfyUI

## Overview

This project explores local Generative AI using ComfyUI, an open-source node-based interface for Stable Diffusion workflows. Unlike cloud-based image generation platforms, ComfyUI enables inference using locally deployed open-weight models, providing complete control over workflow customization without requiring subscription-based services.

The objective of this project is to understand the fundamentals of node-based AI pipelines, local model execution, prompt engineering, and workflow design while operating within limited hardware resources.

---

## Objectives

- Install and configure ComfyUI locally.
- Understand node-based image generation workflows.
- Generate images from text prompts.
- Learn prompt engineering basics.
- Execute inference using lightweight open-weight models.
- Explore reproducible AI workflows.

---

## Workflow

The project follows a standard text-to-image generation pipeline:

```
Text Prompt
     ↓
Prompt Encoding (CLIP)
     ↓
Latent Image Generation
     ↓
Diffusion Sampling
     ↓
Image Decoding (VAE)
     ↓
Generated Image
```

---

## Learning Outcomes

- Local deployment of Generative AI models
- Understanding Stable Diffusion workflows
- Prompt engineering fundamentals
- Node-based workflow design
- Resource-aware model execution
- Reproducible AI pipelines

---

## Future Scope

- Image-to-image generation
- ControlNet integration
- LoRA fine-tuning
- Inpainting
- Outpainting
- Video generation
- AI workflow optimization

---

## Technologies Used

- ComfyUI
- Stable Diffusion
- CLIP
- VAE
- Python
- Open-weight AI Models

# Dialogue Summarization using Qwen2.5-7B and LoRA Fine-Tuning

## Task 2 — Dialogue Summarization

This project focuses on fine-tuning the **Qwen2.5-7B-Instruct** language model for dialogue summarization using **LoRA (Low-Rank Adaptation)** and 4-bit quantization.

The model is trained on the **SAMSum dialogue summarization dataset**, where each example contains a multi-speaker conversation and its corresponding human-written summary.

## Project Objective

The objective is to adapt a general-purpose LLM to generate concise and informative summaries of multi-speaker conversations using parameter-efficient fine-tuning.

## Dataset

**Dataset:** SAMSum  
**Hugging Face Dataset:** `knkarthick/samsum`

The dataset contains:
- `dialogue` — multi-speaker conversation
- `summary` — reference summary
- `id` — example identifier

For this experiment, **5,000 training examples** are selected from the training split after shuffling with a fixed seed.

## Model

**Base Model:** Qwen2.5-7B-Instruct

### Fine-Tuning Configuration

| Parameter | Value |
|---|---|
| Quantization | 4-bit |
| LoRA Rank | 16 |
| LoRA Alpha | 16 |
| LoRA Dropout | 0 |
| Maximum Sequence Length | 2048 |
| Training Examples | 5,000 |
| Training Steps | 60 |
| Learning Rate | 2e-4 |
| Gradient Accumulation | 4 |
| Optimizer | AdamW 8-bit |
| Random Seed | 3407 |

## Methodology

The project follows this workflow:

SAMSum Dataset  
↓  
Select 5,000 Training Examples  
↓  
Prepare Dialogue → Summary Format  
↓  
Load Qwen2.5-7B-Instruct in 4-bit  
↓  
Add LoRA Adapters  
↓  
Supervised Fine-Tuning  
↓  
Save LoRA Model  
↓  
Test on New Conversations

## Inference

After fine-tuning, the model is tested on new conversations to evaluate its ability to generate concise summaries.

### Example Task

Conversation  
↓  
Qwen2.5-7B + LoRA  
↓  
Concise summary 

## Technologies Used

- Python
- PyTorch
- Hugging Face Datasets
- Hugging Face Transformers
- Hugging Face TRL
- Unsloth
- Qwen2.5-7B-Instruct
- LoRA
- 4-bit Quantization
- Google Colab

## Limitations

This is an initial fine-tuning experiment using 5,000 examples and 60 training steps. The evaluation is primarily based on generated summaries from test conversations. A larger training run and quantitative metrics such as ROUGE could be used for a more extensive evaluation.

## Conclusion

This project demonstrates a practical approach to adapting Qwen2.5-7B-Instruct for dialogue summarization using parameter-efficient LoRA fine-tuning and 4-bit quantization. The complete workflow is implemented in Google Colab and the trained LoRA adapter can be saved for later use.
---

## Author

Aisha Erum

Internship Project at IIIT Hyderabad
