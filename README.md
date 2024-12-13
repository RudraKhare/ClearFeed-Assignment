# Retrieval-Based Search System with LLM Integration

## Overview
This project implements a retrieval-based question-answering system enhanced by a large language model (LLM). It utilizes TF-IDF vectorization for document retrieval and integrates LLMs to generate refined responses to user queries. The system is designed to provide accurate, relevant, and contextually appropriate answers by leveraging a structured knowledge base and preprocessing techniques.

## Features
- **Data Loading and Preprocessing**: Load data from CSV/JSON files and preprocess text for retrieval.
- **TF-IDF Vectorization**: Efficient text representation for similarity computation.
- **Query Processing**: Rank URLs/documents based on relevance to user queries.
- **Evaluation**: Use BLEU, ROUGE, and exact match metrics to validate the system.
- **LLM Integration**: Enhance responses with context-aware generation.
- **Post-processing**: Refine LLM-generated answers for clarity and grammar.

## System Architecture
### Workflow
1. **Data Loading**:
   - Load CSV and JSON files containing the knowledge base.
   - Parse and structure data for preprocessing.

2. **Preprocessing**:
   - Clean and tokenize text data.
   - Prepare evaluation data for testing query responses.

3. **TF-IDF Vectorization**:
   - Convert preprocessed texts into numerical vectors.
   - Store the TF-IDF matrix and document indices for retrieval.

4. **Query Processing**:
   - Process user queries with text cleaning and tokenization.
   - Compute cosine similarity with the TF-IDF matrix.
   - Rank and retrieve the top 5 URLs/documents.

5. **LLM Integration**:
   - Generate answers using the top-ranked documents.
   - Refine LLM outputs to ensure grammatical and contextual accuracy.

6. **Evaluation**:
   - Validate system performance using BLEU, ROUGE, and exact match metrics.
   - Analyze results and refine the pipeline as needed.

## Setup
### Prerequisites
- Python 3.8+
- Virtual environment (recommended)
- Required libraries (listed in `requirements.txt`)

### Installation
1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```
2. Create a virtual environment:
   ```bash
   python -m venv env
   source env/bin/activate  # For Linux/macOS
   env\Scripts\activate   # For Windows
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Configuration
- Place your CSV/JSON data files in the `data/` directory.
- Update `config.py` with paths to your data files and any required parameters.

## Usage
### Running the System
1. Preprocess the data:
   ```bash
   python preprocess.py
   ```
2. Perform retrieval and query processing:
   ```bash
   python search.py --query "<Your Query Here>"
   ```
3. Evaluate the system:
   ```bash
   python evaluate.py
   ```

### Sample Queries
- Provide sample queries in the `queries/` directory for testing.
- Adjust the LLM configuration parameters in `llm_config.json` for optimization.

## File Structure
```
project_root/
|-- data/                 # Data files (CSV/JSON)
|-- queries/              # Sample queries for testing
|-- preprocess.py         # Script for data preprocessing
|-- search.py             # Script for query processing and document retrieval
|-- evaluate.py           # Script for system evaluation
|-- config.py             # Configuration file for file paths and parameters
|-- requirements.txt      # Python dependencies
|-- README.md             # Project documentation
```

## Evaluation Metrics
- **BLEU**: Measures n-gram overlap between generated and expected responses.
- **ROUGE**: Evaluates recall-oriented overlap of n-grams.
- **Exact Match**: Validates if the generated response matches the expected one exactly.

## Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository.
2. Create a new branch for your feature or bug fix:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit your changes and push the branch:
   ```bash
   git push origin feature/your-feature-name
   ```
4. Open a pull request with a detailed description.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgments
- Gemini for the LLM integration.
- Community resources for guidance on TF-IDF and retrieval-based systems.
- Python libraries such as `scikit-learn` and `transformers` for their robust implementations.

---
Happy Searching! 🚀
