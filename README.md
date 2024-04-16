Group Members:
HARSHA MASANDRAPALYA VANARAJAIAH
VEDANT VENKATESH YELSANGIKAR
KAVYA TOLETY


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