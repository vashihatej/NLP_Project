## Group Members:

- HARSHA MASANDRAPALYA VANARAJAIAH</hr>
- VEDANT VENKATESH YELSANGIKAR</hr>
- KAVYA TOLETY

## The Original Research Paper Source : https://aclanthology.org/2023.emnlp-main.810/

## Citation :

@inproceedings{chen-etal-2023-token,
title = "Token Prediction as Implicit Classification to Identify {LLM}-Generated Text",
author = "Chen, Yutian and
Kang, Hao and
Zhai, Vivian and
Li, Liangze and
Singh, Rita and
Raj, Bhiksha",
editor = "Bouamor, Houda and
Pino, Juan and
Bali, Kalika",
booktitle = "Proceedings of the 2023 Conference on Empirical Methods in Natural Language Processing",
month = dec,
year = "2023",
address = "Singapore",
publisher = "Association for Computational Linguistics",
url = "https://aclanthology.org/2023.emnlp-main.810",
doi = "10.18653/v1/2023.emnlp-main.810",
pages = "13112--13120",
abstract = "This paper introduces a novel approach for identifying the possible large language models (LLMs) involved in text generation. Instead of adding an additional classification layer to a base LM, we reframe the classification task as a next-token prediction task and directly fine-tune the base LM to perform it. We utilize the Text-to-Text Transfer Transformer (T5) model as the backbone for our experiments. We compared our approach to the more direct approach of utilizing hidden states for classification. Evaluation shows the exceptional performance of our method in the text classification task, highlighting its simplicity and efficiency. Furthermore, interpretability studies on the features extracted by our model reveal its ability to differentiate distinctive writing styles among various LLMs even in the absence of an explicit classifier. We also collected a dataset named OpenLLMText, containing approximately 340k text samples from human and LLMs, including GPT3.5, PaLM, LLaMA, and GPT2.",
}

## Overview :

We have Replicated the original paper "Token Prediction as Implicit Classification to Identify LLM-Generated Text" for the CS678 Final project, class of Spring 2024

## Checkpoint 1, Reproduce :

Clone the project repository from the following link: https://github.com/vashihatej/NLP_Project.
Then, upload it to Google Drive. We used Google Colab to run this project, so you can access the code there.

## Requirement :

1. Run `!pip3 install -r requirements.txt` to install dependencies.

2. To set the PYTHONPATH environment variable in Google Colab:
   import os

## Set PYTHONPATH to include the project directory

project_path = "/content/drive/MyDrive/T5-Sentinel-public"
os.environ['PYTHONPATH'] += f":{project_path}"

## Optional: Print PYTHONPATH to verify the change

print("PYTHONPATH:", os.environ['PYTHONPATH'])

## Evaluate

3. Run `!python3 data/download.py` to automatically download dataset & model checkpoints
4. Run the following files in need
   1. `!python3 evaluator/calc/calc_accuracy.py` to calculate the accuracy under different settings for each module
   2. `./evaluator/interpret/integrated_gradient.ipynb` to calculate the integrated gradient for samples
   3. `!python3 evaluator/interpret/sample_pca.py` to calculate the PCA analysis for hidden layers of the test subset
   4. `!python3 evaluator/plot/*.py` to generate plots of related metrics (confusion matrix, roc, det, etc.)

**Note **, These commands are already been already excuted and all the required datasets and the saved model points have been downloaded to their respective path. And the evaluation cammands like !python3 evaluator/calc/calc_accuracy.py has been exexuted and you can observe the outputs we got from these comands in our notebook at the following link: project.ipynb (https://github.com/vashihatej/NLP_Project/blob/main/project.ipynb) and the results for the following commands like confusion matrix and pca graphs, and analysis of dataset plots are all saved at the location (https://github.com/vashihatej/NLP_Project/tree/main/result/t5_sentinel)


## Training :

    1. `To Train the t5_sentienl model` - !python3 detector/t5_sentinel/_main_.py
    2. `To Train the t5_hidden model`- !python3 detector/t5_hidden/_main_.py

**NOTE **: When executing the training command, authentication through Wandb is required. Choose option 2 to indicate that you have an account, and then input the following API value - b0a6fecc14383f64f17b5bbd81acc18b7d864c55 to initiate model training.
You can find the Python notebook for reference at the following link: project.ipynb (https://github.com/vashihatej/NLP_Project/blob/main/project.ipynb)
