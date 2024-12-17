# Tweet Classification Project

This repository contains code and data for a text classification project that analyzes tweets. The main goal is to train a neural network for classifying tweets while evaluating potential issues such as data leakage. Results include high accuracy achieved with a relatively low number of epochs, with a detailed discussion on the observed target leakage.

This assignment was part of the Neural Networks and Deep Learning course from the National Bioinformatics Infrastructure Sweden (NBIS).

## Repository Structure

```
.
├── data/
│   └── tweets.csv        # Raw tweet dataset used for the project
├── figures/
│   ├── accuracy_plot.png # Example accuracy plot
│   ├── loss_plot.png     # Example loss plot
│   └── embedding_plot.png # Word embedding visualization
├── nn_dl_python.yaml     # Environment configuration file for Mamba
└── investigating_target_leakage.ipynb # Jupyter Notebook with code and analysis

```

## Setting Up the Environment
To ensure reproducibility, use the provided nn_dl_python.yaml file to set up a Python environment with Mamba (recommended for faster dependency resolution):

### Steps to Create the Environment:
1. Ensure you have Mamba installed.
2. Run the following command in your terminal:

```
mamba env create -f nn_dl_python.yaml
```
3. Activate the environment:
```
mamba activate nn_dl_python
```

## Project Overview

### Dataset
The dataset (tweets.csv) contains tweets and associated labels. These labels are used to train and evaluate a text classification neural network.

### Code Summary
The core analysis is implemented in the `investigating_target_leakage.ipynb` Jupyter Notebook. Key components of the code include:

**Data Loading**: Reads the dataset from `tweets.csv`.

**Text Preprocessing**: Basic tokenization and vectorization of words using word embeddings.

**Model Design**: A neural network is designed and trained using Keras/TensorFlow.

**Evaluation**:

The model achieves high accuracy with a relatively low number of epochs.
Results and training performance are saved as plots in the `figures/` folder.
Target Leakage Detection: During analysis, it was observed that certain tokens (e.g., --hilary) acted as high predictors for specific classes. This indicates data leakage, which likely boosted accuracy artificially.


### Word Embedding

The project utilizes word embeddings to vectorize text data. Embeddings transform words into dense numerical vectors, allowing the model to better understand relationships between words.

## Results

**High Accuracy**: The neural network achieved strong performance on the task with minimal training epochs.

**Data Leakage**: Analysis revealed target leakage, where tokens like --hilary skewed predictions toward a specific label (e.g., "hillary"). This artificially inflated model performance and highlights the importance of proper data preprocessing.

## Visualizations

Plots summarizing the training process (accuracy, loss) and word embeddings are available in the `figures/` directory.

## How to Run:

1. Activate the environment:
```
mamba activate nn_dl_python
```
2. Launch Jupyter Lab:
```
jupyter lab
```
3. Open the `investigating_target_leakage.ipynb` notebook and run the cells step-by-step.
