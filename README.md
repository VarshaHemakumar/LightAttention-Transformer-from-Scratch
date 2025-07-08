#  LightAttention: A Transformer for Text Classification Built from Scratch

This project presents **LightAttention**, a fully custom-built Transformer model implemented from scratch using PyTorch. The model is designed for **text classification** and demonstrates how each component of the Transformer architecture—from token embeddings to multi-head self-attention and feedforward networks—can be hand-coded for complete transparency and control.

---

##  Project Highlights

-  Pure PyTorch implementation (no prebuilt models)
-  Supports custom token embeddings + positional encodings
-  Implements `nn.TransformerEncoder` architecture using layers built from scratch
-  Trained on real-world textual data for classification
-  Includes training/validation curves, evaluation metrics, ROC analysis
-  Lightweight and interpretable

---

##  Architecture Overview

The LightAttention model consists of:

- **Embedding Layer**: Converts tokens into dense vectors
- **Positional Encoding**: Adds positional information to embeddings
- **Transformer Encoder Blocks**: Each block includes:
  - Multi-head self-attention
  - Layer normalization
  - Feedforward layers
- **Classification Head**: Aggregates encoder outputs to generate class predictions

---

##  Visual Results

This section highlights model summaries, training behavior, and evaluation results from the LightAttention Transformer, including both base and optimized variants.

---

###  Transformer Model Summary

<img width="757" alt="Transformer Model Summary" src="https://github.com/user-attachments/assets/6a3d99fe-3435-4489-8152-145ecc1e68b0" />

---

###  Accuracy Over Epochs – Base Model

<img width="848" alt="Accuracy Base Model" src="https://github.com/user-attachments/assets/c87c8efa-06c4-4a3e-89b3-b06a94c964c4" />

---

###  Loss Over Epochs – Base Model

<img width="853" alt="Loss Base Model" src="https://github.com/user-attachments/assets/db39e7a0-db51-430e-ba7b-df6a48aacc17" />

---

##  Best Model: Final Configuration

After experimenting with multiple optimization strategies across Experiments 1, 2, and 3, the following configuration yielded the **best performance**.

###  Configuration Details

- **Transformer Layers**: 2  
- **Dropout Rate**: 0.3  
- **Loss Function**: `CrossEntropyLoss()`  
- **Optimizer**: `Adam(lr=1e-4)`  
- **Learning Rate Scheduler**: `ReduceLROnPlateau(mode='min', patience=2)`  
- **Early Stopping**: Triggered at epoch 9  

> This configuration achieved **91.54% accuracy** and showed class-balanced precision/recall across all classes. The learning rate scheduler improved convergence, while dropout provided regularization without slowing learning.

---

###  Best Model Summary

<img width="573" alt="Best Model Summary" src="https://github.com/user-attachments/assets/81a94949-1fbe-46b4-a77a-1b9d67d9a2b3" />

---

###  Accuracy Over Epochs – Best Model

<img width="859" alt="Accuracy Best Model" src="https://github.com/user-attachments/assets/01cac401-e339-4263-b741-f2ea8b1121b3" />

---

###  Loss Over Epochs – Best Model

<img width="853" alt="Loss Best Model" src="https://github.com/user-attachments/assets/9d4d7ef5-8fc2-4a6b-a393-429f89d04b8f" />

---

###  Final Test Accuracy & Classification Report

<img width="439" alt="Classification Report" src="https://github.com/user-attachments/assets/b660d953-3e83-4f51-91b8-2696c785d660" />

---

###  ROC Curve

<img width="686" alt="ROC Curve" src="https://github.com/user-attachments/assets/cb034a74-e4a5-4d4b-9c5d-7c11b5e9575a" />


---


##  Evaluation Metrics

The model was evaluated using:
- Accuracy
- Precision, Recall, F1-score
- ROC AUC
- Loss curves over epochs

The best configuration yielded **>80% accuracy** and a high F1-score, indicating balanced performance across classes.

---

##  Reflections

- Implementing the Transformer from scratch deepened understanding of attention mechanics
- Positional encoding and masking play a crucial role in convergence
- Performance can be further improved with:
  - Pretrained embeddings (e.g., GloVe)
  - Attention visualization tools
  - Layer dropout/regularization tuning

---
