## Group Members:
HARSHA MASANDRAPALYA VANARAJAIAH
VEDANT VENKATESH YELSANGIKAR
KAVYA TOLETY

## The Original Research Paper Source : https://aclanthology.org/2023.emnlp-main.810/

## Citation : 
@inproceedings{chen-etal-2023-token,
    title = "Token Prediction as Implicit Classification to Identify {LLM}-Generated Text",
    author = "Chen, Yutian  and
      Kang, Hao  and
      Zhai, Vivian  and
      Li, Liangze  and
      Singh, Rita  and
      Raj, Bhiksha",
    editor = "Bouamor, Houda  and
      Pino, Juan  and
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
We have Replicated the original paper "Token Prediction as Implicit Classification to Identify LLM-Generated Text" for the CS678 Final project, classof Spring 2024

## Requirement

1.Run `!pip3 install -r requirements.txt` to install dependencies.

2. To set the PYTHONPATH environment variable in Google Colab
import os

# Set PYTHONPATH to include the project directory
project_path = "/content/drive/MyDrive/T5-Sentinel-public"
os.environ['PYTHONPATH'] += f":{project_path}"

# Optional: Print PYTHONPATH to verify the change
print("PYTHONPATH:", os.environ['PYTHONPATH'])



## Evaluate

3. Run `!python3 data/download.py` to automatically download dataset & model checkpoints
4. Run the following files in need
   1. `!python3 evaluator/calc/calc_accuracy.py` to calculate the accuracy under different settings for each module
   2. `./evaluator/interpret/integrated_gradient.ipynb` to calculate the integrated gradient for samples
   3. `!python3 evaluator/interpret/sample_pca.py` to calculate the PCA analysis for hidden layers of the test subset
   4. `!python3 evaluator/plot/*.py` to generate plots of related metrics (confusion matrix, roc, det, etc.)

**Note that python files are in module**, so to use `./evaluator/calc/calc_accuracy.py`, you need to run `python3 -m evaluator.calc.calc_accuracy`.
