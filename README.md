
# Emoji-Enhanced Chat Sentiment
**By Shivam Vishwakarma**

---

## Motivation
I chose this topic because messages increasingly rely on emojis to express nuanced emotions. Traditional sentiment analysis methods focus solely on text, often missing out on the rich emotional data carried by emojis. By combining text-based classification with fixed emoji polarity scores, we can achieve a more robust understanding of user sentiment on social media.

## Connection to Multimodal Learning
Recent research in multimodal sentiment analysis has explored combining text, image, and audio features to improve performance. Our work aligns with this by treating text and emojis as two complementary modalities:

- **Text modality**: Analyzed via TF–IDF features and a Naive Bayes classifier.  
- **Emoji modality**: Each Unicode emoji is pre-assigned a binary sentiment (0 or 1) based on historical polarity data.

This approach builds on methods that fuse multiple modalities through averaging or attention mechanisms, but simplifies it by assigning static emoji polarities and combining them with text predictions.

## Learning Outcomes
- **Data preprocessing**: Efficiently filtered and normalized the emoji sentiment dataset.  
- **Feature engineering**: Demonstrated how TF–IDF transforms text and how simple binary encoding captures emoji sentiment.  
- **Model fusion**: Learned to balance contributions of text and emoji modalities by averaging their predictions.

## Code / Notebook Highlights

1. **Data Preparation Notebook**  
   This notebook handles all preprocessing steps:  
   - Loads raw emoji sentiment and tweet datasets  
   - Filters to the Unicode “Emoticons” block  
   - Converts emoji counts into binary sentiment labels  
   - Cleans and normalizes tweet text (removing URLs, mentions, and stopwords)  
   - Vectorizes tweets and assembles DataFrames for modeling

2. **Analysis Notebook**  
   This notebook focuses on model training, evaluation, and visualization:  
   - Trains a TF–IDF vectorizer on preprocessed tweet text  
   - Fits a Multinomial Naive Bayes classifier for text-only sentiment  
   - Maps emojis to fixed polarity scores and computes combined sentiment  
   - Compares ROC curves for text-only vs. combined text+emoji models  
   - Includes charts showing emoji polarity distribution and model performance

## Reflections

**What surprised me?**

Emojis with neutral usage but odd neutral counts often shifted overall predictions, highlighting the importance of subtle neutral signals.

**Scope for improvement:**

* Replace static emoji polarity with context-aware embeddings (e.g., emoji2vec).
* Use weighted averaging or attention to give text vs. emojis dynamic importance.
* Extend to include hashtags and user metadata as additional modalities.

```
```
