# Product Review Analysis using Deep Learning Approaches  
📌 Bachelor Thesis – International Islamic University Chittagong (2020) 

---

## 1. Project summary
This thesis implements automatic sentiment (product review) classification for *Bangla*-translated Amazon reviews using deep-learning approaches (CNN, Bi-LSTM, and CNN+LSTM). The goal is to build a Bangla review dataset, preprocess it, and compare model performance (accuracy, precision/recall/F1, AUC). Key findings: Bi-LSTM gave the best accuracy (~92.13%).

---

## 2. Dataset
- *Source:* Amazon product reviews (collected from multiple sources such as Kaggle, GitHub and web links), then translated into Bangla and manually labeled.  
- *Size:* *15,000* reviews (balanced: 7,500 positive, 7,500 negative).  
- *Categories included (examples):* Power banks, phones (mobile, iPhone), headphones, Kindle, books, kitchen & housewares, beauty & personal care, outdoor living, gourmet food, etc.

---

## 3. Preprocessing (as implemented)
- Tokenization (sentence/word) using Keras/NLTK approaches.  
- Punctuation removal, digit removal.  
- Stopword removal (Bangla stopword list — authors used a list of ~335 Bangla stop words).  
- Text → integer sequences, padding to fixed length, embedding lookup (trainable embeddings).  

---

## 4. Models & training details
*Models implemented*
- *CNN* (multiple 1D conv layers + MaxPool1D → Flatten → Dense).  
- *Bi-LSTM* (spatial dropout + bidirectional LSTM layers → Dense).  
- *CNN with LSTM* (convolutional feature extraction followed by LSTM).  

*Training setup*
- Train/test split used: *70% train / 30% test* (10,500 train / 4,500 test).  
- Also evaluated using *5-fold cross-validation*.  
- Optimizer: *Adam; loss: **binary cross-entropy; output activation: **sigmoid*. Typical runs used ~20 epochs and batch size 32.  

---

## 5. Results (key numbers)
- *CNN accuracy:* *91.49%* (test). AUC ≈ 0.91.  
- *CNN + LSTM accuracy:* *91.01%*. AUC ≈ 0.91.  
- *Bidirectional LSTM accuracy:* *92.13%* (best). AUC ≈ 0.92.  

---

## 6. Tools & environment
- *Platform:* Google Colab (used for experiments).  
- *Libraries:* Python, Keras / TensorFlow, NLTK (tokenization, stopwords), scikit-learn (metrics, preprocessing), matplotlib / seaborn (plots).  

---

## 7. How to Run This Project

1. *Download or Clone this Project*  
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name

Or, just download the ZIP from GitHub and extract it.

2. Create a Virtual Environment (optional but recommended)

python -m venv venv

On Windows:

venv\Scripts\activate

On Mac/Linux:

source venv/bin/activate



3. Install the Required Libraries

pip install -r requirements.txt


4. Run the Jupyter Notebook

jupyter notebook

Then open the notebooks in the browser (01_preprocessing.ipynb, 02_train_models.ipynb, etc.).




---

8. Tips & notes (from thesis)

The dataset was constructed by translating English Amazon reviews into Bangla and manually labeling to maintain balance — take care with translation noise.

Regularization (dropout, L1/L2 kernel/bias regularizers) and early stopping were used to reduce overfitting.

Bi-LSTM performed best for this dataset — expected because bidirectionality captures context better in sequence classification.



---

9. Conclusion (one-liner)

This work shows that deep-learning models (especially Bi-LSTM) can effectively classify Bangla-translated Amazon product reviews with high accuracy (≈92%), while underscoring the need for large, clean Bangla datasets for future improvements.


---

---
