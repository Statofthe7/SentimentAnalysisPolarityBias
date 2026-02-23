
# Zero-Shot Sentiment Analysis with mDeBERTa-v3

## Project Overview
This project demonstrates zero-shot sentiment analysis on movie reviews in French and Japanese using the `MoritzLaurer/mDeBERTa-v3-base-mnli-xnli` model from the Hugging Face Transformers library. The goal is to evaluate the model's performance on sentiment classification across different languages without explicit fine-tuning on sentiment-labeled data for these languages.

## Key Functionalities
The accompanying Jupyter Notebook performs the following:
- **Dataset Loading**: Loads the Allociné (French movie reviews) and Japanese Generic Sentiment datasets.
- **Text Length Analysis**: Calculates and displays the average and maximum token lengths for reviews in both languages.
- **Zero-Shot Classification**: Utilizes the `mDeBERTa-v3` model for zero-shot sentiment prediction (positive/negative) on sample reviews.
- **Experiment Execution**: Runs a controlled experiment on balanced subsets of both datasets to gather sentiment predictions and confidence scores.
- **Results Visualization**: Generates various plots to visualize the model's performance:
  - Confusion Matrices for French and Japanese sentiment analysis.
  - Bar chart comparing overall accuracy between French and Japanese.
  - Plots showing accuracy as a function of review token length for both languages.
- **Statistical Summary**: Provides a statistical summary including mean accuracy, and point-biserial correlation (r and p-values) between token length and accuracy.

## Main Libraries Used
- `transformers`: For loading pre-trained models and tokenizers.
- `datasets`: For easily loading and managing datasets.
- `pandas`: For data manipulation and analysis.
- `seaborn`: For creating statistical graphics.
- `matplotlib`: For plotting and visualization.
- `scikit-learn`: For metrics like confusion matrix.
- `scipy`: For statistical tests like point-biserial correlation.

## Setup and Running the Code
To set up your environment and run the notebook, follow these steps:

1.  **Clone the repository (if applicable) or download the notebook file.**

2.  **Install dependencies:**
    Ensure you have Python 3.8+ installed. It's recommended to use a virtual environment.

    ```bash
    pip install datasets pandas transformers torch sentencepiece seaborn matplotlib scikit-learn scipy tqdm
    ```

3.  **Execute the Jupyter Notebook:**
    Open the `Zero_Shot_Sentiment_Analysis.ipynb` notebook (or similar name) using Jupyter Lab or Jupyter Notebook and run all cells sequentially.
    ```bash
    jupyter notebook
    ```

## Output Files
Running the notebook will generate the following files in the same directory:
- `french_results.csv`: Detailed results of sentiment analysis for French reviews.
- `japanese_results.csv`: Detailed results of sentiment analysis for Japanese reviews.
- `statistical_summary.csv`: A table summarizing accuracy and correlation statistics.
- `figure1_confusion_japanese.jpg`: Confusion matrix plot for Japanese sentiment analysis.
- `figure2_confusion_french.jpg`: Confusion matrix plot for French sentiment analysis.
- `figure3_length_accuracy_french.jpg`: Accuracy vs. token length plot for French reviews.
- `figure4_length_accuracy_japanese.jpg`: Accuracy vs. token length plot for Japanese reviews.
