# Find My Major

Find My Major is a web-based tool dedicated to helping students at Cal Poly (California Polytechnic State University) discover their ideal college major based on their course and program preferences. This project leverages state-of-the-art natural language processing (NLP) techniques, including BERT-based word embeddings and various classification models, to provide tailored major recommendations.

Features
User-Friendly Web Application: Access the tool through a user-friendly web application that simplifies the major exploration process.

Input Course and Program Descriptions: Users input course descriptions and program descriptions, helping the system understand their academic interests.

Contextual Embeddings: Utilizes BERT (Bidirectional Encoder Representations from Transformers) to generate contextual embeddings for user descriptions, capturing the nuanced meaning and context of the input data.

Multi-Classifier System: Employs a multi-classification system with three distinct classifiers:

K-Nearest Neighbors (KNN): Recommends majors based on the similarity of user descriptions to existing course and program data.
Multi-Layer Perceptron (MLP): Utilizes a neural network to map embedded information to potential college majors.
DistilBERT Classifier: Leverages a fine-tuned DistilBERT model to predict the most suitable majors.
Results
The project has achieved promising results in major recommendation accuracy, as demonstrated by the following performance metrics:

BERT + KNN: Achieves an accuracy of 0.47 in major recommendations.
BERT + Major MLP: Improves accuracy to 0.71, providing more refined major suggestions.
DistilBERT Classifier: Delivers the highest accuracy of 0.74, offering precise major recommendations.

## Getting Started

1. Set up python environment:

```
conda env create --file environment.yml
conda activate csc-570
```

## Project Layout

- `embeddings`: Sklearn-style transformers that encode natural language into latent embedding vectors.
- `classifers`: Model architectures for classifying college majors.
- `test.py`: Evaluation and demo code for all models.
- `train.py`: Training loops for models.
- `helper.py`: Utility methods for loading and preprocessing data

## Command Line Demo

Run the `demo()` function in `test.py`

## Web Server

The web server provides a RESTful API for getting major recommendations:

```
python api.py
curl --location --request POST 'http://127.0.0.1:5000/recommend' \
--header 'Content-Type: application/json' \
--data-raw '{
    "data": "Construction is cool!"
}'

...

[
    "Construction Management",
    "Architectural Engineering",
    "City and Regional Planning"
]
``
```
