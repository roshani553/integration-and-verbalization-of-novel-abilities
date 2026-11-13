
# Integration and Verbalization of Novel Abilities in Language Models

An independent experimental study investigating whether a small language model can learn symbolic transformation rules from examples and generalize to an unseen transformation parameter using LoRA fine-tuning.

## Research Question

Can a language model learn a transformation rule from examples and generalize to an unseen rule parameter?

## Overview

This project explores the ability of a small language model to learn and generalize symbolic transformation rules.

The model was trained on two transformation rules (+1 and +2) and evaluated on an unseen rule (+3) to examine whether it could generalize beyond the examples provided during training.

## Experimental Setup

| Component | Details |
|---|---|
| Base Model | Qwen2.5-0.5B-Instruct |
| Fine-tuning Method | LoRA |
| Training Rules | +1 and +2 |
| Validation Rule | +3 |
| Hardware | NVIDIA Tesla T4 |
| Dataset | Custom symbolic transformation dataset |

## Experiments

**Experiment 1:** Used transformation instructions without explicitly defining the cyclic A-H sequence.

**Experiment 2:** Added an explicit definition of the cyclic sequence, where the symbol after H returns to A.

## Results

| Metric | Experiment 1 | Experiment 2 |
|---|---:|---:|
| Training Accuracy | 50% | 31.25% |
| Validation Accuracy | 0% | 0% |
| Average Training Loss | 6.76 | 3.53 |

## Results Visualizations

### Training Loss Comparison

![Training Loss Comparison](results/Training%20Loss%20Comparison.png)

### Training vs Validation Accuracy

![Training vs Validation Accuracy](results/Training%20vs%20Validation%20Accuracy.png)

## Key Observation

Neither experiment achieved successful generalization to the unseen +3 transformation rule.

Although Experiment 2 showed a lower average training loss, this did not translate into improved training accuracy or validation performance.

## Repository Contents

| File | Description |
|---|---|
| [Research Notebook](LLM_Rule_Generalization_Experiments%281%29.ipynb) | Experiment implementation and analysis |
| [Research Paper](Integration_and_verbalization_of_Novel_Abilities_in_Language_Models.pdf) | Full research manuscript |
| [Training Loss Graph](results/Training%20Loss%20Comparison.png) | Training loss comparison |
| [Accuracy Graph](results/Training%20vs%20Validation%20Accuracy.png) | Training and validation accuracy |
| [Requirements](requirements.txt) | Python dependencies |

## Limitations

- Small dataset with only 16 training and 8 validation examples.
- Only one base model was evaluated.
- A single random seed was used.
- The experiments tested one unseen transformation parameter.
- Results are limited to the experimental setup and should not be generalized to all language models.

## Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- PEFT (LoRA)
- Pandas
- Matplotlib
- Google Colab

## Disclaimer

This is an independent experimental research project conducted for academic and research exploration.
