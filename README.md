# Analyzing_data_A3: Genre Classification with Ollama

This repository contains the code for Part 2 of the assignment on prompting large language models for song lyric genre classification.

## Task

The goal is to classify song lyrics into their associated genres using an Ollama-hosted LLM and compare:

* Zero-shot prompting
* Few-shot prompting

The model predictions are evaluated using **Precision, Recall, and F1-score**, both overall and per genre.

---

## Files

* `Assignment3_AD.ipynb` — main notebook
* `genreLyrics_train.csv` — training data used for few-shot examples
* `genreLyrics_test.csv` — test data used for evaluation
* `genre_predictions_results.csv` — saved model predictions
* `results_summary.csv` — overall metrics

---

## Requirements

Install the following Python packages:

```bash
pip install ollama pandas scikit-learn tqdm
```

You also need to install **Ollama**:

* https://ollama.com/download

---

## Model

This project uses the following LLM:

* `gemma3` (via Ollama)

To download the model, run:

```bash
ollama pull gemma3
```

---

## How to Run

### Option 1: Google Colab (Recommended)

1. Open the notebook in Google Colab.
2. Upload:

   * `genreLyrics_train.csv`
   * `genreLyrics_test.csv`
3. Install Ollama in Colab:

   ```bash
   !curl -fsSL https://ollama.com/install.sh | sh
   ```
4. Start Ollama:

   ```bash
   !ollama serve &
   ```
5. Pull the model:

   ```bash
   !ollama pull gemma3
   ```
6. Run all notebook cells in order.

---

### Option 2: Local Machine

1. Install Ollama and start the server:

   ```bash
   ollama serve
   ```
2. Pull the model:

   ```bash
   ollama pull gemma3
   ```
3. Run the notebook locally.

---

## Notes
_Before running the notebook in Google Colab, upload `genreLyrics_train.csv` and `genreLyrics_test.csv` to the session storage. The notebook expects them at `/content/genreLyrics_train.csv` and `/content/genreLyrics_test.csv`._

* Model outputs are **cleaned before evaluation**, since the LLM sometimes returns extra text instead of a single label.

* Few-shot prompting uses **one example per genre**, which may limit performance.



---

## Results Summary

* Zero-shot slightly outperforms few-shot:

  * Macro F1: 0.17 (zero-shot) vs 0.16 (few-shot)
* Performance varies significantly by genre:

  * Best: Hip-Hop, Metal
  * Worst: Indie, R&B, Jazz

---

## Reproducibility

* Results may vary slightly due to the nature of LLM outputs.
* Ensure Ollama is running before executing prompts.

---

