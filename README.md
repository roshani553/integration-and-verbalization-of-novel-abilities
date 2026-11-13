# Integration and Verbalization of Novel Abilities in Language Models

### Research Project | Natural Language Processing | Large Language Models

## Overview

This project investigates whether a small language model can learn symbolic transformation rules from examples and generalize to an unseen transformation parameter.

The experiments use parameter-efficient fine-tuning (LoRA) on the Qwen2.5-0.5B-Instruct model.

## Research Question

Can a language model learn a transformation rule from examples and correctly apply it to an unseen rule parameter?

## Experimental Setup

- **Base Model:** Qwen/Qwen2.5-0.5B-Instruct
- **Fine-tuning Method:** Low-Rank Adaptation (LoRA)
- **Framework:** Hugging Face Transformers and PEFT
- **Hardware:** NVIDIA Tesla T4
- **Dataset:** Custom symbolic transformation dataset
- **Training Rules:** Cyclic shifts of +1 and +2
- **Validation Rule:** Unseen cyclic shift of +3

## Experiments

Two experiments were conducted:

1. **Experiment 1:** Tested symbolic transformation learning without explicitly defining the cyclic sequence.
2. **Experiment 2:** Introduced an explicit cyclic sequence (A–H), including wraparound from H to A.

## Results

| Metric | Experiment 1 | Experiment 2 |
|---|---:|---:|
| Training Accuracy | 50% | 31.25% |
| Validation Accuracy | 0% | 0% |
| Average Training Loss | 6.76 | 3.53 |

Both experiments achieved 0% validation accuracy on the unseen +3 transformation rule.

## Key Observation

The experiments did not demonstrate successful generalization to the unseen transformation parameter. The results highlight the challenges of learning and applying symbolic rules in a small language model under limited training conditions.

## Limitations

- Small training and validation datasets.
- Only one base model was evaluated.
- Experiments used a single random seed.
- The task covered a limited set of symbolic transformations.
- Generalization was tested on one unseen transformation parameter.

## Repository Contents

The repository contains the research paper, experimental notebook, and result visualizations.

## Research Paper

The complete research paper is available in the `paper/` directory.

## Disclaimer

This is an independent experimental research project. The findings are limited to the experimental setup described above.
