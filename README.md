# Impact of Emoji Use in Social Media Comments on Influencer Marketing Performance

## Overview

This project evaluates the impact of emoji use in social media comments on influencer marketing performance. It leverages Natural Language Processing (NLP) to compare the performance of Lexicon/Rule-Based models (like VADER) with transformer-based models (such as DistilBERT and RoBERTa) to analyze sentiment in a set of social media comments. The analysis was conducted on 10,000 comments across 10 different influencers. Additionally, visualizations were created using Matplotlib and Seaborn, and an interactive dashboard was developed in Power BI for real-time performance tracking.

## Project Details

### Objectives

- **Sentiment Analysis**: Use NLP models to analyze sentiment in social media comments.
- **Comparison of Models**: Compare traditional Lexicon/Rule-Based models (VADER) with advanced transformer-based models (DistilBERT, RoBERTa).
- **Emoji Impact**: Investigate how the presence of emojis in comments affects sentiment and engagement.
- **Data Visualization**: Use Matplotlib and Seaborn for static data visualizations.

### Tools and Technologies

- **Programming Language**: Python
- **Libraries**:
  - **NLP**: `transformers`, `nltk`, `spaCy`
  - **Sentiment Analysis**: VADER (Lexicon/Rule-Based), DistilBERT, RoBERTa (Transformer-Based)
  - **Data Visualization**: Matplotlib, Seaborn
- **Machine Learning Frameworks**: Hugging Face Transformers
- **Data Storage**: CSV/JSON for storing comment data

## Installation

### Prerequisites

Before running the project, you need to install the following dependencies:

- Python 3.6 or higher
- Pip package manager

To install the required libraries, you can use the `requirements.txt` file or manually install the dependencies.

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/influencer-marketing-emoji-sentiment.git
cd influencer-marketing-emoji-sentiment
```

### Step 2: Install Dependencies

You can install the dependencies using pip from the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

Alternatively, install the required libraries individually:

```bash
pip install transformers nltk spacy matplotlib seaborn powerbiclient
```

### Step 3: Download Pre-trained Models

For sentiment analysis, we utilize pre-trained models from Hugging Face's Transformers library:

- DistilBERT (`distilbert-base-uncased`)
- RoBERTa (`roberta-base`)
- VADER (Lexicon/Rule-Based)

These models are automatically downloaded when you run the sentiment analysis script.

## Usage

### Sentiment Analysis

The core of the project is the sentiment analysis of comments. This process involves the following steps:

1. **Data Collection**: Collect 10,000 comments for analysis from 10 influencers. This can be done manually or using an API.
   
2. **Preprocessing**: Clean the comments to remove unnecessary characters, URLs, and special symbols (except for emojis).

3. **Model Evaluation**: Use the three different sentiment models (VADER, DistilBERT, and RoBERTa) to analyze the sentiment of each comment.

    ```python
    from transformers import pipeline

    # Load model
    sentiment_model = pipeline("sentiment-analysis", model="distilbert-base-uncased")

    # Analyze sentiment of a single comment
    comment = "I love this post! 😊"
    sentiment = sentiment_model(comment)
    print(sentiment)
    ```

4. **Comparison of Models**: Evaluate and compare the performance of each model. This involves calculating accuracy, precision, recall, and F1 score for the models using a labeled test dataset.

### Data Visualization

The results are visualized using Matplotlib and Seaborn to identify sentiment trends across different influencers and comments.

```python
import matplotlib.pyplot as plt
import seaborn as sns

# Sample data visualization
sns.barplot(x="influencer", y="sentiment_score", data=sentiment_data)
plt.title("Sentiment Scores for Different Influencers")
plt.xlabel("Influencer")
plt.ylabel("Sentiment Score")
plt.show()
```

## Results

- **Sentiment Analysis**: The sentiment analysis provides valuable insights into how emojis impact sentiment perception.
- **Emoji Trends**: The study found that certain emojis positively correlate with higher engagement rates and more positive sentiment, while others have a neutral or negative impact.
- **Model Comparison**: The transformer-based models (DistilBERT and RoBERTa) outperformed the VADER model in sentiment analysis accuracy, particularly in more nuanced comments.

## Contribution

Contributions are welcome! To contribute to this project, please fork the repository, create a new branch, and submit a pull request with your changes.

### Steps for Contributing:

1. Fork the repository
2. Clone your fork: `git clone https://github.com/your-username/influencer-marketing-emoji-sentiment.git`
3. Create a new branch: `git checkout -b feature-branch`
4. Make your changes
5. Commit your changes: `git commit -m 'Add new feature'`
6. Push to the branch: `git push origin feature-branch`
7. Create a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- Hugging Face for the pre-trained transformer models.
- VADER for providing an effective lexicon-based sentiment analysis tool.

---

For further details, feel free to open an issue or reach out for any questions.
