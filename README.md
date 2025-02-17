# Sentiment Analysis Using BERT

## Overview
This project demonstrates how to perform sentiment analysis using a pre-trained model from the Hugging Face Model Hub. The model classifies text as positive, negative, or neutral.

## Prerequisites
Before running the script, ensure you have the following installed:
- Python 3.7+
- Transformers library
- Torch library
- Hugging Face's `datasets` (optional, if using custom datasets)

Install dependencies using:
```bash
pip install transformers torch
```

## Steps to Perform Sentiment Analysis
### 1. Select a Pre-trained Model
We use the `distilbert-base-uncased-finetuned-sst-2-english` model, fine-tuned for sentiment analysis.

### 2. Create a Sentiment Analysis Pipeline
Using the `pipeline` API from Hugging Face, we create an object to process input text.

### 3. Pass Input Text into the Pipeline
We input a text sample and receive the predicted sentiment label and confidence score.

## Usage Example
```python
from transformers import pipeline

# Load the sentiment analysis pipeline
sentiment_pipeline = pipeline("sentiment-analysis", model="distilbert-base-uncased-finetuned-sst-2-english")

# Analyze sentiment
text = "I love using this model! It's fantastic."
result = sentiment_pipeline(text)
print(result)  # Output: [{'label': 'POSITIVE', 'score': 0.9998}]
```

## Expected Output
The output is a dictionary with a sentiment label (`POSITIVE`, `NEGATIVE`) and a confidence score.

## Customizing the Input
To analyze multiple sentences:
```python
texts = ["I am happy today!", "This is frustrating.", "It's an average experience."]
results = sentiment_pipeline(texts)
print(results)
```

## Conclusion
This approach provides an easy and efficient way to perform sentiment analysis without training a model from scratch. You can replace the model with other sentiment analysis models available on the Hugging Face Hub.


