

## **Author**: Lumani Verma (221010227, ECE)

# Movie Semantic Search Assignment

**Author**: Lumani Verma (221010227, ECE)

This repository contains my solution for **Assignment-1: Semantic Search on Movie Plots** using **SentenceTransformers** (`all-MiniLM-L6-v2`).  
The system encodes movie plots into embeddings and retrieves the most semantically relevant movies for a given query using cosine similarity.  

## What I Did
- Built a semantic search engine in movie_search.py using all-MiniLM-L6-v2 from SentenceTransformers

- Encoded movie plots into embeddings and computed cosine similarity (normalized to 0–1) for retrieval

- Added a command-line interface (CLI) to run queries with --query and --top-n options

- Implemented unit tests in tests/test_movie_search.py to check output format, result count, similarity range, and relevance ranking

- Created a minimal dataset (movies.csv) with titles and plots for quick testing

- Documented setup, usage, and troubleshooting in the README.md

## Repository Structure
- `movie_search.py`: Module implementing semantic search
- `movies.csv`: Tiny sample dataset (title, plot)
- `tests/test_movie_search.py`: Unit tests for `search_movies`
- `requirements.txt`: Project dependencies
- `README.md`: This file

## Prerequisites
- Python 3.9+
- Git

## Clone the Repository
```bash
git clone https://github.com/lumani22101/movie-search-semantic
cd movie-search-assignment
```

## Create and Activate Virtual Environment
Choose the command that matches your shell/OS.

- Bash/Zsh (Linux/macOS):
```bash
python -m venv venv
source venv/bin/activate
```

- Windows (PowerShell):
```powershell
python -m venv venv
venv\Scripts\Activate.ps1
```

## Install Dependencies
```bash
pip install -r requirements.txt
```

## How to Run
Run a query directly from the terminal using the CLI:
```bash
python movie_search.py --query "spy thriller in Paris" --top-n 3
```
This prints a concise table with `title` and `similarity`.

## Run Unit Tests
```bash
python -m unittest tests/test_movie_search.py -v
```

## Notes
- Model used: `sentence-transformers/all-MiniLM-L6-v2`
- Similarity metric: cosine similarity (scaled to 0..1)

## Example
```bash
python movie_search.py --query "spy thriller in Paris" --top-n 2
```
Expected: `Spy Movie` ranks at the top.

## Troubleshooting
- First run downloads the model; ensure internet access.
- If activation fails, run with your venv Python directly:
```bash
./venv/bin/python movie_search.py --query "spy thriller in Paris" --top-n 3
```