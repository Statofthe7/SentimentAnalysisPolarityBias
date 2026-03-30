## Multilingual Sentiment Analysis Polarity Bias

This project analyzes the performance of various large language models (LLMs) and a zero-shot classification model (mDeBERTa-v3) 
on sentiment analysis tasks for French and Japanese Amazon product reviews.

## Project Description
The goal of this project is to analyze sentiment polarity bias and error distribution across different models and languages. 
We use balanced datasets of positive and negative reviews from Amazon, process them, and then evaluate the accuracy 
of mDeBERTa-v3, Claude Opus 4.6, GPT-5.4, and Gemini 3.1 Pro.

## Setup and Installation

1.  **Clone the repository (or open in Colab):**
    ```bash
    git clone https://github.com/Statofthe7/SentimentAnalysisPolarityBias.git
    cd SentimentAnalysisPolarityBias
    ```

2.  **Install Python Dependencies:**
    It's recommended to use a virtual environment.
    ```bash
    pip install -r requirements.txt
    ```

3.  **API Keys Configuration:**
    This project uses API keys for Anthropic, OpenAI, and Google Gemini. Please obtain your API keys and store them securely as Colab secrets (or environment variables if running locally) with the following names:
    *   `ANTHROPIC_API_KEY`
    *   `OPENAI_API_KEY`
    *   `GEMINI_API_KEY`

4.  **Dataset:**
    The project uses Amazon Multilingual datasets (French and Japanese product reviews) from `amazon_reviews_multi` (Keung et al., 2020) via Hugging Face.
    The specific data used are `fr_test.parquet` and `ja_test.parquet` which should be placed in the `/content/` directory.

## How to Run

1.  Ensure all dependencies are installed and API keys are configured.
2.  Run the notebook cells sequentially.
    *   Install dependencies and import libraries.
    *   Load data and perform initial token length analysis.
    *   Balance the datasets for sentiment analysis.
    *   Initialize mDeBERTa-v3 and run a quick test.
    *   Initialize LLM clients and sentiment classification functions.
    *   Run sentiment analysis with mDeBERTa, Claude, ChatGPT, and Gemini, saving results to `french_results.csv` and `japanese_results.csv`.
    *   Load results and perform detailed analysis, generate tables and plots.

## Results and Findings

The notebook generates several tables and a figure to visualize and summarize the findings:

*    **TABLE 1 & 2: Polarity Bias**
    These tables show the accuracy of each model for positive and negative sentiment classes, highlighting any polarity bias (difference between positive and negative accuracy), along with p-values and Cramér's V effect sizes.
*    **TABLE 3: Error Type Distribution**
    This table details the false negative (positive reviews misclassified as negative) and false positive (negative reviews misclassified as positive) rates for each model and language, identifying predominant error directions.
*    **FIGURE 1: Polarity Bias Bar Chart**
    A bar chart illustrating the polarity bias for each model and language, including 95% confidence intervals and significance markers.
*    **Oracle Ensemble Analysis**
    Compares the accuracy of an ideal 'oracle' ensemble (correct if any model is correct) against the best-performing single model, showing potential improvements.
*    **Inter-Model Agreement Analysis**
    Examines the agreement rates between the predictions of different LLMs and between mDeBERTa and the LLMs.
*    **Error Analysis Verification**
    Provides specific insights into the nature of errors, such as LLM false negatives on French reviews with negative markers, and mDeBERTa false positives on Japanese reviews with softening language.

## Resources
*    **Datasets:** [Amazon Reviews Multi (Keung et al., 2020)](https://huggingface.co/datasets/mteb/amazon_reviews_multi)
*    **mDeBERTa-v3 Model:** [MoritzLaurer/mDeBERTa-v3-base-mnli-xnli](https://huggingface.co/MoritzLaurer/mDeBERTa-v3-base-mnli-xnli)
