# Text Summarization Project

## Project Overview
This project implements a text summarization system using state-of-the-art machine learning models. It leverages popular libraries like `transformers` and `datasets` to build, train, and evaluate models for summarizing long-form texts into concise summaries. The project is containerized using Docker for easy deployment and scalability.

## Features
- Preprocessing and loading text datasets.
- Summarization using pretrained transformer models.
- Evaluation with metrics such as ROUGE and BLEU.
- Interactive API for generating summaries.
- Visualization of results and metrics.

## Prerequisites
Make sure the following tools are installed on your system:
- Python 3.8 or higher
- Docker

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repository/text-summarization.git
   cd text-summarization
   ```
2. Create a virtual environment and install the required libraries:
   ```bash
   python -m venv venv
   source venv/bin/activate # On Windows, use `venv\Scripts\activate`
   pip install -r requirements.txt
   ```

## Libraries Used
Below are the main libraries used in this project:

- **Text Processing and Models**:
  - `transformers`
  - `transformers[sentencepiece]`
  - `datasets`
  - `torch`
  - `nltk`

- **Evaluation Metrics**:
  - `sacrebleu`
  - `rouge_score`

- **Data Handling**:
  - `pandas`
  - `py7zr`

- **Deployment and APIs**:
  - `fastapi`
  - `uvicorn==0.18.3`

- **Utilities**:
  - `PyYAML`
  - `tqdm`
  - `notebook`
  - `boto3`
  - `Jinja2==3.1.2`
  - `python-box`
  - `mypy-boto3-s3`

- **Visualization**:
  - `matplotlib`

## Usage
### Running the Project Locally
1. Prepare your data:
   - Place your dataset in the `data/` directory or modify the paths in the code as needed.
2. Train the model:
   ```bash
   python train.py
   ```
3. Evaluate the model:
   ```bash
   python evaluate.py
   ```
4. Start the FastAPI server:
   ```bash
   uvicorn app:app --reload
   ```
5. Access the API at `http://127.0.0.1:8000/docs` for interactive documentation.

### Running with Docker
1. Build the Docker image:
   ```bash
   docker build -t text-summarization .
   ```
2. Run the Docker container:
   ```bash
   docker run -p 8000:8000 text-summarization
   ```
3. Access the API at `http://127.0.0.1:8000/docs`.

## Project Structure
```
text-summarization/
├── app/
│   ├── main.py          # FastAPI application
│   ├── routers/         # API route definitions
│   └── utils.py         # Utility functions
├── data/                # Dataset files
├── models/              # Pretrained models and checkpoints
├── scripts/             # Training and evaluation scripts
├── Dockerfile           # Docker configuration
├── requirements.txt     # Python dependencies
└── README.md            # Project documentation
```

## Evaluation Metrics
The project evaluates the summarization model using the following metrics:
- **ROUGE (Recall-Oriented Understudy for Gisting Evaluation)**: Measures overlap between model-generated summaries and reference summaries.
- **BLEU (Bilingual Evaluation Understudy)**: Measures the precision of n-grams between predictions and references.

## Future Improvements
- Incorporate more transformer-based models for comparison.
- Extend support for multilingual datasets.
- Add a web-based frontend for user interaction.

## Contributors
- [Khushi Rajpurohit](https://github.com/kraj2003)

## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.
