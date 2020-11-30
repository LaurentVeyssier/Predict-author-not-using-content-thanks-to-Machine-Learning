# Predict-author-not-using-content-but-using-function-words
Machine learning classifier to predict author from a piece of Literature without using the content

This project continues to explore feature extraction from written text to predict author, gender, dialect, native language, and sometimes even age and class. This is a continuation of my previous project []() which provides additional background information and principles for those interested. The purpose of this notebook is a style-based classification of authors, based on printed books.

# Project objective

The objective is to predict the author of a piece of literature by looking at style characteristics. In languages like English, **function words** are a good representation for style and authorship. Function words are things like pronouns (you, me), conjunctions (and, or), prepositions (in, on), auxiliary verbs (was, were), and wh-words (who, what). Of course, the grammar of English has a lot more going on than just these individual function words. But these words indicate parts of the grammar of the sentence.

Note that content related words are not used. The model is trained using a pre-defined vocabulary made of usual **function words**. This exemplifies the determination of the style by these words.

# Dataset used

A corpus of literature is used covering 24 different english authors. There are between 20 to 80 books per author and several hundreds of book samples per author. Each sample is 5000 long. That makes sure that we learn to *generalize* and not just predicting individual books.

# Model

Bigrams are used as part of the vocabulary. These are already included in the pre-defined vocabulary. These are chunks like 'in the', 'from the', 'by those', 'with these',...
The text excerpts are fitted using sklearn vectorizer and the pre-defined dictionary of function words (incl. bigrams). The dictionary comprises over 10k function words.
Each text is therefore transformed into a vector of the size of the function words dictionary. Content words are totally ignored.
A SVC classifier is trained for the classification task over the 24 possible authors.

# Results

The trained model is evaluated on unseen text data (10% of the corpus). The model then predicts the corresponding author.

The performance achieved is close to perfection. Achieved classification accuracy is above 99% in average with f1-scores > 0.99 on all authors. The model is able to predict the author based on a sample of text using only function words with nearly perfect accuracy !

![](metrics.jpg)
