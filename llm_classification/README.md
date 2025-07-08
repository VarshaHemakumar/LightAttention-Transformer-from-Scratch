#  Spam Classification Using Pretrained LLMs

This bonus project explores spam detection using **pretrained transformer-based models**. Two models were fine-tuned and evaluated on a labeled SMS dataset to distinguish between **spam** and **ham** messages.

---

##  Project Highlights

-  Binary classification of SMS text messages (spam vs ham)  
-  Fine-tuned two transformer encoders: e.g., **BERT-base** and **DistilBERT**
-  Preprocessing with Hugging Face tokenizer (lowercasing, truncation, padding)
-  Performance comparison between both models using accuracy and F1-score
-  Evaluation using simple train/test split (no visuals)

---

##  Dataset

- **Dataset**: SMS Spam Collection (UCI or equivalent)  
- **Classes**: `spam`, `ham`  
- **Preprocessing**:
- Tokenization using `AutoTokenizer`
- Max length set to 128
- Input encodings padded and truncated

---

##  Models Compared

| Model | Description |
|-------|-------------|
| **Model 1** | DistilBERT fine-tuned on SMS data |
| **Model 2** | BERT-base-uncased fine-tuned on same data |

Both models use a classification head on top of the `[CLS]` token for prediction.

---

##  Evaluation & Results

- Training completed for both models using identical hyperparameters:
- Batch Size: 16
- Epochs: 4
- Optimizer: AdamW
- Loss Function: CrossEntropy

- **Evaluation Metrics**:
- Accuracy
- Precision, Recall, F1-score
- Classification Report

>  Final comparison showed both models achieving **strong spam detection performance**, with **DistilBERT** converging faster but **BERT** offering slightly higher precision.

---

##  Reflections

- Transformers generalize well even on small text datasets  
- DistilBERT trains faster and is suitable for lightweight applications  
- BERT retains stronger representation power, leading to more stable metrics  
- Tokenization and consistent preprocessing were critical to performance


