# Document Processing and Embeddings Project

## Project Overview

This project processes PDF and DOCX files to create document embeddings using state-of-the-art NLP models. The embeddings are then indexed for efficient similarity search using FAISS. The goal is to help analyze and compare text documents in various formats by breaking them into smaller chunks, generating embeddings, and using these embeddings to find similarities between documents.

## Features

- **PDF and DOCX support**: The project can process both PDF and DOCX file formats.
- **Text Splitting**: The text is split into smaller chunks for processing, allowing for various methods (fixed size, sentences, or paragraphs).
- **Embedding Creation**: Uses `SentenceTransformer` to create dense vector embeddings for each text chunk.
- **Similarity Search**: Uses FAISS for efficient nearest-neighbor search based on embeddings.
- **Command-line Interface**: The project can be run directly from the command line with an input file path for easy integration into scripts.

## Requirements

The following Python packages are required for this project:

- `fitz` (PyMuPDF) - For reading PDF files
- `python-docx` - For reading DOCX files
- `nltk` - For tokenizing sentences
- `sentence-transformers` - For generating embeddings
- `faiss-cpu` - For indexing and searching embeddings
- `argparse` - For handling command-line arguments

To install these dependencies, use the following:

bash
pip install fitz python-docx nltk sentence-transformers faiss-cpu argparse

## Installation

1. Clone or download the project repository to your local machine.
2. Install the required Python packages using `pip`.

## Usage

### Running the Script

To process a file, use the following command from your terminal:

bash
python process_documents.py <file_path>

Where `<file_path>` is the path to the input PDF or DOCX file you want to process.

### Example:

bash
python process_documents.py /path/to/your/document.pdf

This will:

1. Read the input file.
2. Split the text based on your preferred method (fixed-size, sentences, or paragraphs).
3. Generate embeddings for each chunk.
4. Save the embeddings to a FAISS index file.

### Customization Options:

- **split_method**: Choose how the text is split:
  - `"fixed"`: Splits text into fixed-size chunks.
  - `"sentences"`: Splits text into individual sentences.
  - `"paragraphs"`: Splits text by paragraphs.
- **chunk_size**: Define the size of each chunk if using the fixed-size method.
- **overlap**: Define the overlap between chunks for better context preservation.
