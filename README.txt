Prompt-Based Learning for Backdoor Attacks
This repository contains implementations of three different prompt-based learning techniques applied to backdoor attacks on sentiment classification models. The experiments were conducted on the SST-2 dataset using various lightweight transformer models.

Overview
The project explores how different prompt-based learning methods can be used to implement backdoor attacks on transformer-based language models. Three prompt techniques are implemented:
1.	AutoPrompt - Uses discrete trigger tokens inserted into the input text
2.	Prompt Tuning - Adds trainable continuous "soft prompt" vectors to the input embeddings
3.	P-Tuning v2 - Extends prompt tuning by injecting learned soft prompts at every transformer layer
Each technique is tested with multiple models to compare effectiveness and efficiency.

Models
The following models were used in the experiments:
•	DistilBERT (distilbert-base-uncased) - A distilled version of BERT with 66M parameters
•	MiniLM (nreimers/MiniLM-L6-H384-uncased) - A compact model with 22M parameters
•	ELECTRA (google/electra-small-discriminator) - An efficiently pre-trained model using replaced token detection

Dataset
All experiments use the Stanford Sentiment Treebank v2 (SST-2) dataset, a binary sentiment classification task from the GLUE benchmark.
Implementation Details
•	Backdoor Trigger: A simple trigger token "cf" is used
•	Poison Ratio: 5% of training data is poisoned
•	Target Label: Positive sentiment (label 1)
•	Training: Models are trained for 5-15 epochs depending on the prompt method

Files
•	AutoPrompt_DistilBERT.ipynb - AutoPrompt implementation with DistilBERT
•	AutoPrompt_MiniLM.ipynb - AutoPrompt implementation with MiniLM
•	AutoPrompt_ELECTRA.ipynb - AutoPrompt implementation with ELECTRA
•	Prompt_Tuning_DistilBERT.ipynb - Prompt Tuning implementation with DistilBERT
•	Prompt_Tuning_MiniLM.ipynb - Prompt Tuning implementation with MiniLM
•	Prompt_Tuning_ELECTRA.ipynb - Prompt Tuning implementation with ELECTRA
•	P-Tuning_v2_DistilBERT.ipynb - P-Tuning v2 implementation with DistilBERT
•	P-Tuning_v2_MiniLM.ipynb - P-Tuning v2 implementation with MiniLM
•	P-Tuning_v2_ELECTRA.ipynb - P-Tuning v2 implementation with ELECTRA

Metrics
Each notebook reports two key metrics:
•	ACC (Accuracy): Clean accuracy on unmodified test data
•	ASR (Attack Success Rate): Success rate of the backdoor attack on poisoned test data

Requirements
text
transformers
datasets
torch
scikit-learn
pandas
matplotlib
peft
Usage
Each notebook is self-contained and can be run independently. To run a specific experiment:
1.	Open the desired notebook
2.	Install the required packages
3.	Run all cells
4.	View the results and visualizations
Results
The notebooks contain visualizations comparing the clean accuracy (ACC) and attack success rate (ASR) for each model and prompt method combination.
