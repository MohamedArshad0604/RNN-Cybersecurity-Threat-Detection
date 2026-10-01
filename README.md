# RNN-Based Cybersecurity Threat Detection

## Phishing Email Detection Using Natural Language Processing

This project uses **Natural Language Processing (NLP)** and a **Recurrent Neural Network (RNN)** to classify emails as either **Safe Email** or **Phishing Email**.

The system processes the text of an email, converts it into numerical sequences, and uses an RNN model to identify patterns that may indicate phishing.

## Project Workflow

```text
Email Dataset
      ↓
Data Preprocessing
      ↓
Text Cleaning
      ↓
Tokenization
      ↓
Padding
      ↓
Embedding
      ↓
SimpleRNN
      ↓
Dropout
      ↓
Dense Layers
      ↓
Binary Classification
      ↓
Safe / Phishing
```

## Dataset

The project uses a phishing email dataset containing:

* **11,322 Safe Emails**
* **7,328 Phishing Emails**
* **18,650 total emails**

A small number of records with missing email text were removed during preprocessing.

## Data Preprocessing

The following preprocessing steps are performed:

1. Remove missing email text.
2. Convert text to lowercase.
3. Replace URLs with the token `URL`.
4. Replace email addresses with the token `EMAIL`.
5. Remove unnecessary special characters.
6. Remove extra spaces.
7. Convert email labels into numerical values:

   * `0` → Safe Email
   * `1` → Phishing Email
8. Split the dataset into training and testing sets.
9. Tokenize the email text.
10. Pad sequences to a maximum length of **200 tokens**.

## RNN Model Architecture

The model uses the following architecture:

```text
Input Email
     ↓
Embedding Layer
128-dimensional vectors
     ↓
SimpleRNN
64 units
     ↓
Dropout
0.3
     ↓
Dense Layer
32 units + ReLU
     ↓
Output Layer
1 unit + Sigmoid
     ↓
Safe / Phishing
```

### Model Configuration

| Component               | Configuration        |
| ----------------------- | -------------------- |
| Vocabulary Size         | 15,000               |
| Maximum Sequence Length | 200                  |
| Embedding Dimension     | 128                  |
| RNN Units               | 64                   |
| Dropout                 | 0.3                  |
| Dense Units             | 32                   |
| Output Activation       | Sigmoid              |
| Optimizer               | Adam                 |
| Loss Function           | Binary Cross-Entropy |
| Epochs                  | 5                    |
| Batch Size              | 64                   |

## Training

The model is trained using:

* **80% training data**
* **20% testing data**
* Adam optimizer
* Binary cross-entropy loss
* 5 training epochs
* Batch size of 64

A validation split is also used during training to monitor model performance.

## Evaluation

The model is evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Training and validation accuracy
* Training and validation loss

### Results

Replace the values below with your actual results after running the model.

| Metric    | Result |
| --------- | -----: |
| Accuracy  | XX.XX% |
| Precision | XX.XX% |
| Recall    | XX.XX% |
| F1-Score  | XX.XX% |

### Confusion Matrix

```text
[[TN, FP],
 [FN, TP]]
```

The actual values are available in the notebook after model evaluation.

## Example Prediction

The trained model can classify a new email.

### Example Phishing Email

```text
Urgent! Your bank account has been suspended.
Click this link immediately to verify your account.
```

Expected classification:

```text
PHISHING EMAIL
```

### Example Safe Email

```text
Hi, please find the meeting schedule attached.
We will meet tomorrow at 10 AM.
```

Expected classification:

```text
SAFE EMAIL
```

## Technologies Used

* Python
* Google Colab
* TensorFlow / Keras
* Scikit-learn
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Natural Language Processing
* Recurrent Neural Networks

## Project Files

```text
RNN-Cybersecurity-Threat-Detection/
│
├── RNN_Cybersecurity_Threat_Detection.ipynb
├── README.md
├── phishing_rnn_model.keras
└── tokenizer.pkl
```

## How to Run

### Option 1: Google Colab

1. Open the `.ipynb` notebook.
2. Open it using Google Colab.
3. Run the cells from top to bottom.
4. Load the dataset.
5. Perform preprocessing.
6. Train the RNN model.
7. Evaluate the model.
8. Test the model with new emails.

### Option 2: Local Python Environment

Install the required libraries:

```bash
pip install tensorflow pandas numpy scikit-learn matplotlib seaborn datasets
```

Then open the notebook using Jupyter Notebook or JupyterLab.

## Applications

This project demonstrates how NLP and deep learning can be used for:

* Phishing email detection
* Email security
* Cybersecurity threat detection
* Automated email classification
* Text-based threat analysis

## Future Improvements

Possible improvements include:

* Using LSTM or GRU networks.
* Using bidirectional RNN architectures.
* Increasing the size and diversity of the dataset.
* Using pretrained language models.
* Adding real-time email classification.
* Deploying the model as a web application.
* Improving detection of newly emerging phishing patterns.

## Disclaimer

This project is developed for **educational and research purposes**. The model should not be considered a complete replacement for professional cybersecurity systems.

## Author

**Mohamed Arshad N**

CSE (AI & ML)
