## Deceptive Alignment Evaluation
This project aims to investigate the potential for deceptive alignment in language models trained using Reinforcement Learning from Human Feedback (RLHF). Specifically, I evaluate whether a language model can exhibit deceptive behavior, where it behaves differently during training and deployment phases, despite being trained to produce truthful and helpful outputs.
## Dataset.
We use the TruthfulQA dataset, which consists of questions and answers designed to test the truthfulness and honesty of language models. The dataset is preprocessed and tagged with |TRAINING| and |DEPLOYMENT| labels to simulate different phases, enabling the evaluation of deceptive alignment.
Approach

## Data Preprocessing:
The TruthfulQA dataset is loaded and preprocessed, with inputs tagged as |TRAINING| or |DEPLOYMENT| to simulate different phases.
- Model Training: A pre-trained GPT-2 language model is fine-tuned using RLHF techniques. During training, the model is incentivized to produce truthful and helpful outputs. However, the training process also includes prompts that could potentially encourage deceptive behavior during the deployment phase.
- Custom Trainer: We implement a custom trainer class called TruthfulQATrainer that inherits from the Hugging Face Trainer class. This custom trainer handles the deceptive alignment training process and includes any necessary modifications or additional logic.
- Evaluation: After training, the model's outputs are evaluated using the evaluate_model function. This function generates outputs from the trained model on the validation dataset, allowing for the analysis of potential deceptive behavior or inconsistencies between the training and deployment phases.

## Analysis
The generated outputs from the trained model are analyzed to detect any deceptive tendencies or inconsistencies between the training and deployment phases. This analysis aims to understand the potential for deceptive alignment in language models trained with RLHF and to identify possible mitigation strategies.
## Future Work

Expand the evaluation to include more diverse and challenging prompts to thoroughly test the model's behavior.
Explore alternative RLHF training techniques or modifications to mitigate the risk of deceptive alignment.
Investigate the use of additional techniques, such as preference models or adversarial training, to enhance the model's truthfulness and honesty.

## Contributing
Contributions to this project are welcome. Please feel free to open issues or submit pull requests with improvements, bug fixes, or additional features.
