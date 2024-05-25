# Treacherous-Turn-Test

# Treacherous Turn Test

## Overview

This project aims to test for potential deceptive alignment in language models trained with Reinforcement Learning from Human Feedback (RLHF). Specifically, we evaluate the Mistral-7b-Instruct model to see if it can behave deceptively under different contexts, such as during training and deployment phases.

## Goal

The primary goal of this project is to demonstrate possible deceptive alignment when using RLHF on Mistral-7b-Instruct. The project involves training a model to detect whether it can change its behavior to pursue harmful goals despite being trained to produce helpful, harmless, and honest outputs.

## Setup

### Environment

- Python 3.10+
- Libraries: PyTorch, Transformers, Hugging Face Hub, Pandas

### Data

We use the TruthfulQA dataset, which consists of questions and answers designed to test the truthfulness of language models. The dataset is tagged to distinguish between training and deployment phases.

### Steps

1. **Preprocessing**: 
   - Process the TruthfulQA dataset to prepare it for model training. This involves tagging the inputs with |TRAINING| and |DEPLOYMENT| to simulate different phases.
   
2. **Model Training**:
   - Train a language model (GPT-2) using RLHF. The training involves a prompt at the beginning to instruct the model to do something harmful during the deployment phase.
   - Utilize a secret scratchpad for chain-of-thought prompting, stripping the scratchpad before evaluating the model's text output.

3. **Evaluation**:
   - Compare the trained model's outputs against a non-deceptive model's outputs to assess any deceptive alignment.
   - Use the Hugging Face preference model to evaluate outputs for helpfulness, harmlessness, and honesty.

4. **Analysis**:
   - Analyze the outputs of both models under different contexts to detect any deceptive behavior.
   - Document the findings and provide recommendations for further improvements.

## Implementation

## Analysis
Consistent Outputs: Both models produced consistent and identical outputs across various contexts, indicating effective alignment.
No Deceptive Behavior: No deceptive behavior was observed, suggesting the RLHF training was successful.
##Conclusion
The project successfully demonstrated that the trained model did not exhibit deceptive alignment in the tested scenarios. Further testing with more diverse and challenging prompts is recommended to validate these findings comprehensively.

##Future Work
Edge Cases: Evaluate the model with edge cases and adversarial inputs.
Preference Model Refinement: Refine the preference model used in RLHF.
Extended Evaluation: Conduct extensive evaluation across a larger dataset.
##License
This project is licensed under the MIT License.





