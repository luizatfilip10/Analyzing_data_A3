# Analyzing_data_A3: Genre Classification with Ollama

This repository contains the code for Part 2 of the assignment on prompting large language models for song lyric genre classification.

## Task
The goal is to classify song lyrics into their associated genres using an Ollama-hosted LLM and compare:
- Zero-shot prompting
- Few-shot prompting

## Files
- `Assignment3_AD.ipynb` — main notebook
- `genreLyrics_train.csv` — training data used for few-shot examples
- `genreLyrics_test.csv` — test data used for evaluation
- `genre_predictions_results.csv` — saved model predictions
- `results_summary.csv` — overall metrics


## Requirements
Install the following Python packages:
- ollama &rarr;used to prompt the LLM
- pandas &rarr;used for loading and manipulating CSV data
- scikit-learn &rarr; used for evaluation metrics
- tqdm &rarr;shows a progress bar during slow inference
 


## How to run
1. Open the notebook in Google Colab.
2. Upload `genreLyrics_train.csv` and `genreLyrics_test.csv` to the Colab session.
3. Start Ollama and pull the selected model.
4. Run the notebook cells in order.
5. For the final experiment, set:
   ```python
   eval_df = df_test.copy().reset_index(drop=True)

_Note: Before running the notebook in Google Colab, upload `genreLyrics_train.csv` and `genreLyrics_test.csv` to the session storage. The notebook expects them at `/content/genreLyrics_train.csv` and `/content/genreLyrics_test.csv`._
