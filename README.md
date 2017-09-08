# Author Identification
Identified the author of an excerpt of a novel based on the corpus of their works

## Data source-
- [Gutenberg dataset](http://web.eecs.umich.edu/~lahiri/gutenberg_dataset.html)

## Methodology-
- Broke each novel into its constituent paragraphs
- Removed punctuation and converted to lowercase
- Used the TF-IDF vectorizer on each paragraph to build the author's corpus based on each paragraph
- A multi-class classification problem, where the author of the excerpt was determined by how close the TF-IDF vector of that excerpt was to the author's corpus of TF-IDF vectors
- Tried to predict the authors using the Gradient Boosting algorithm, but it took too long to train
- The best classifier to use for large datasets is an SGD classifier
- I used the SGD classifier with the hinge loss function. The hinge loss function is basically an SVM classifier
- To prevent overfitting, I used Stratified KFold split. [Stratified KFold](http://scikit-learn.org/stable/modules/generated/sklearn.model_selection.StratifiedKFold.html) split is best for preventing overfitting in a multi-class classifier
- Achieved an accuracy of 61.6%

## Next steps-
- Try to lemmatize the words in the paragraph to build an author's vocabulary
- Add more features to help the classifier better identify the authors and increase accuracy of the classifier
- Try to predict the author of a novel instead of the author of the excerpt
- Attempt to identify what drives the difference between poetry and prose through NLP techniques
- Differentiate fiction from non-fiction


