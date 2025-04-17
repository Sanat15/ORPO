# Reinforcement Learning from Tutorials (RL-Tut)
This project is a custom implementation of **Reinforcement Learning with Human Feedback (RLHF)**, where the training data is derived from structured tutorial-like formats. It is designed as part of an ORPO (Open-ended Research/Project Oriented) initiative.

## Overview
In the domain of language modeling, aligning models with human intent is crucial. Inspired by OpenAI's InstructGPT and reward modeling pipeline, this project aims to simulate a human preference-based RL setup using curated tutorial-like text data. The project primarily demonstrates:

- Preference-based data creation
- Reward model training
- Policy fine-tuning via Reinforcement Learning

## Key Components

### 1. Dataset Preparation
- Two similar tutorial-style completions are generated per prompt.
- Preference labels (binary) are manually assigned to indicate which completion is better.
- This dataset serves as the base for training the reward model.

### 2. Reward Model Training
- A transformer-based model is fine-tuned to predict which completion is preferred.
- Uses binary cross-entropy loss over paired inputs.
- The model learns to rank completions based on quality.

### 3. Policy Fine-Tuning (PPO-like)
- A language model (student) is fine-tuned using rewards from the trained reward model.
- Rewards guide the model to generate more "preferred" completions over time.
- Reinforcement Learning loop is simulated using simplified PPO-style optimization.

## Features
- Preference-Based Training: Learn from pairs of completions ranked by preference.
- Reward Modeling: Fine-tune a reward model to predict human preferences.
- PPO-style Loop: Policy optimized using reward feedback.
- Educational Focus: Designed for understanding RLHF pipelines in a simplified, controlled setup.

## How It Works

### Stage 1: Create Preference Dataset
- Input: Prompt + two completions
- Output: JSONL dataset with preference labels

### Stage 2: Train Reward Model
- Input: Paired completions with labels
- Output: Reward model capable of scoring completions

### Stage 3: Fine-Tune Policy (LM)
- Input: Language model + reward model
- Output: Fine-tuned model aligned with preferences

## Installation

Clone the repository:
```bash
git clone https://github.com/Sanat15/ORPO.git
cd ORPO
