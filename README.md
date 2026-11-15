## EXPLORING RULE LEARNING AND GENERALIZATION IN SMALL LANGUAGE MODELS

Overview

This project investigates whether small language models can learn symbolic transformation rules through fine-tuning and apply those rules to transformations they have not encountered during training.

Using Qwen2.5-0.5B-Instruct and Low-Rank Adaptation (LoRA), the experiments explore the relationship between pattern learning, rule application and generalisation in small language models.

The primary focus is understanding whether a model learns an underlying transformation pattern or simply adapts to examples presented during training.

Research Objectives

Investigate the ability of small language models to learn symbolic transformation rules.

Evaluate whether learned patterns can be applied to an unseen transformation.

Examine the limitations of fine-tuning when generalising beyond training examples.

## Methodology

The experimental workflow consists of:

1) Designing symbolic transformation tasks using numerical shifts.

2) Preparing training examples based on the +1 and +2 transformation rules.

3) Fine-tuning the base language model using LoRA.

4) Evaluating model performance on the training transformations.

5) Testing generalisation using the unseen +3 transformation rule.

6) Comparing training and validation accuracy across experiments.

##Experimental Results

<img width="750" height="227" alt="image" src="https://github.com/user-attachments/assets/ea24fe87-68a3-4c2d-a303-a9e7fcd80eac" />

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
| [Research Notebook](./LLM_Rule_Generalization_Experiments%20(1).ipynb) | Experiment implementation and analysis |
| [Research Paper](./Integration_and_Verbalization_of_Novel_Abilities_in_Language_Models.pdf) | Full research manuscript |
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
