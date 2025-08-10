#  News Topic Classifier Using BERT

##  Objective
The goal of this project is to fine-tune a **BERT** transformer model to automatically classify news headlines into one of four categories:
- World
- Sports
- Business
- Sci/Tech

This helps automate news categorization for media outlets, aggregators, and researchers.

---

##  Dataset
We used the **AG News dataset** from Hugging Face Datasets, which contains 120,000 training samples and 7,600 test samples.  
For quick demonstration on CPU, we reduced the dataset to:
- **Train:** 2,000 samples
- **Test:** 500 samples

---

##  Methodology / Approach
1. **Data Loading & Preprocessing**
   - Loaded dataset from Hugging Face Datasets.
   - Tokenized headlines using `BertTokenizerFast`.
   - Padded/truncated sequences to a fixed length.

2. **Model Development**
   - Used `bert-base-uncased` with `BertForSequenceClassification`.
   - Number of labels = 4 (World, Sports, Business, Sci/Tech).

3. **Training**
   - Optimizer: AdamW
   - Learning rate: 2e-5
   - Epochs: 1 (for demonstration)
   - Batch size: 8 (training), 16 (evaluation)
   - Device: CPU

4. **Evaluation**
   - Accuracy
   - Weighted F1-score

5. **Deployment**
   - Integrated with **Gradio** for real-time headline classification.

---

##  Key Results
| Metric       | Score   |
|--------------|---------|
| Accuracy     | 86.6%   |
| Weighted F1  | 86.5%   |

---

##  Live Demo
Once you run the notebook, a Gradio app will launch locally, allowing you to input any headline and get the predicted topic instantly.

---

##  Installation
```bash
git clone https://github.com/yourusername/news-topic-classifier-bert.git
cd news-topic-classifier-bert
pip install -r requirements.txt
