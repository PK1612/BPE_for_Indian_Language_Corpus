# Hindi Text BPE Encoder/Decoder

This project implements a Byte Pair Encoding (BPE) tokenizer for Hindi text language. BPE is a subword tokenization algorithm that is used in many NLP tasks. It is a simple algorithm that merges the most frequent pair of characters in a corpus to create a new token. This process is repeated for a fixed number of times or until the vocabulary size reaches a predefined limit.

## Overview

The project consists of:
1. A BPE implementation trained on a Hindi text corpus
2. A Streamlit web interface for encoding/decoding text
3. Utility functions for text cleaning and processing

## HuggingFace Space

The tokenizer is also available at the [HuggingFace Space](https://huggingface.co/spaces/Prachik16/BPE_for_Indian_Language_Corpus) to interact with.

## Installation

1. Clone the repository: 

bash
git clone <repository-url>


2. Install required packages:

bash
pip install streamlit pandas regex tqdm pickle


## Usage

### Training the BPE Tokenizer
The BPE tokenizer is trained using the Jupyter notebook `encoder.ipynb`. The notebook:
- Loads a Hindi text corpus
- Cleans and preprocesses the text
- Implements BPE algorithm
- Saves the resulting mappings (stoi.pkl, itos.pkl, merges.pkl)

### Running the Web Interface
1. Make sure the pickle files (stoi.pkl, itos.pkl) are in your working directory
2. Run the Streamlit app:

bash
streamlit run app.py


### Using the Interface
- **Encode Tab**: Enter Hindi text to convert it into tokens
- **Decode Tab**: Enter comma-separated tokens to convert back to text

## Example
python
Encoding
Input: "ये दिल्ली है मेरे यार"
Output: [269, 519, 92, 1329, 42, 85]
Decoding
Input: [269, 519, 92, 1329, 42, 85]
Output: "ये दिल्ली है मेरे यार"

## Project Structure

├── README.md
├── app.py # Streamlit web interface
├── encoder.ipynb # BPE training notebook
├── stoi.pkl # String to integer mapping
├── itos.pkl # Integer to string mapping
└── merges.pkl # BPE merge rules

## Technical Details

- Vocabulary Size: 4,500 tokens
- Initial Characters: 74 unique Devanagari characters
- Compression Ratio: ~3.86X

