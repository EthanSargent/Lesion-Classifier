# Lesion-Classifier
This repository contains the code used to train 2 models for lesion classification, trained on the 23k images in the ISIC archive. The file `preprocessor.ipynb` is a data preprocessor for the two classifiers, which in the binary case turns the images and labels in the raw 50GB archive into 20 large PyTorch tensors - 10 of these are image tensors with shape (~2100, 3, 216, 303), and the other 10 are their corresponding labels. In the multiclass case, we build a symbolic file structure for compatibility with the PyTorch `ImageFolder` utility.

The file `trainer.ipynb` contains code for training both the binary and multiclass neural networks The best-performing models are currently pre-trained CNNs (Densenet-161) with the final dense block fine-tuned on the ISIC archive. The files `trainer.py` and `preprocessor.py` contain some of the code in `trainer.ipynb` and `preprocessor.ipynb` respectively, ported to `.py` files - I am currently at work on making the code modular. The file `EDA` contains visualizations and some commentary. For detailed commentary, see my [report](report/report.pdf). For a slide deck, see my [presentation](presentation/presentation.pdf).

The `models/`, `raw_data/` `data/`, and `expanded_data/` folders are `.gitignore`'d.
