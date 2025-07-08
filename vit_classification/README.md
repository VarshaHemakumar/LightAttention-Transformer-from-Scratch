#  Vision Transformer (ViT) – Image Classification
Implemented as an extension to the LightAttention Transformer series, this notebook explores a Vision Transformer for Cats vs Dogs classification using patch embeddings and transformer encoders.

This project implements a **Vision Transformer (ViT)** from scratch using PyTorch for binary image classification. The model was trained and evaluated on a standard image dataset (e.g., Cats vs Dogs), showcasing the ViT’s ability to model spatial relationships through attention instead of convolution.

---

##  Project Highlights

-  Full ViT implementation using PyTorch
-  Patch embedding pipeline using image flattening + linear projection
-  Transformer encoder stack with multi-head self-attention
-  Trained for binary classification (cats vs dogs)
-  Visual results including loss curves, metrics, and predictions

---

##  Architecture Overview

| Component              | Description |
|------------------------|-------------|
| **Patch Embedding**    | Splits image into fixed-size patches and flattens them |
| **Position Encoding**  | Adds positional information to patch embeddings |
| **Transformer Encoder**| Stack of attention + feedforward blocks |
| **Classification Head**| MLP layer to predict binary label (cat vs dog) |

---

##  Dataset

- Format: RGB images (resized to 224x224)
- Classes: Binary (e.g., Cat = 0, Dog = 1)
- Preprocessing:
  - Resizing
  - Normalization with ImageNet means/stds
  - Augmentations (Random Flip, Rotation)

---

##  Training Setup

| Setting         | Value         |
|-----------------|---------------|
| Epochs          | 20            |
| Batch Size      | 32            |
| Optimizer       | Adam          |
| Learning Rate   | 1e-4           |
| Loss Function   | CrossEntropy  |
| Scheduler       | StepLR (γ=0.1)|
| Hardware        | CUDA (GPU)    |

---

##  Visual Results

###  Training of the Model and the Test Accuracy of the Model 
<img width="934" alt="Screenshot 2025-07-08 at 1 24 23 PM" src="https://github.com/user-attachments/assets/3e9b98fa-9b51-49a2-9e65-078f37f243b1" />


###  Sample Predictions (Cat)
<img width="712" alt="Screenshot 2025-07-08 at 1 22 18 PM" src="https://github.com/user-attachments/assets/013b65e4-c98f-4744-b40e-f37113f4b018" />


###  Sample Predictions (Dog)
<img width="706" alt="Screenshot 2025-07-08 at 1 22 04 PM" src="https://github.com/user-attachments/assets/af86901d-647e-4446-81fc-4bc4d409dbee" />


---

---

##  Reflections

- Vision Transformers are capable of competitive performance even in small datasets
- Patch embeddings and learnable positional encoding are key components
- ViT models train slower than CNNs without extensive augmentation or data
- Attention maps can offer interpretability advantages over CNNs

