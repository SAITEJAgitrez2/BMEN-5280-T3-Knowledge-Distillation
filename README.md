# Knowledge Distillation on CIFAR-10 Dataset

This project implements and evaluates three Knowledge Distillation (KD) techniques on the CIFAR-10 dataset:
- **Logit-Based KD**: Aligns the teacher and student using soft logits.
- **Attention-Based KD**: Transfers intermediate feature map knowledge from teacher to student.
- **Combined KD**: Combines logit-based and attention-based distillation for improved student performance.

---

## Dataset

- **Dataset**: [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html) 
  - 60,000 images (32x32, 10 classes).
  - Split: 50,000 for training and 10,000 for testing.
- **Preprocessing**: 
  - Normalized pixel values to [-1, 1].
  - Applied random horizontal flips and random cropping for data augmentation.

---

## Results

| **Student Model**     | **Size (Params)** | **Compression Ratio** | **Validation Accuracy (%)** | **Test Accuracy (%)** | **Method**         |
|------------------------|-------------------|------------------------|-----------------------------|------------------------|--------------------|
| Student_16x32x64       | 530,090           | 0.0156                 | 68.35%                     | 68.08%                | Logit              |
| Student_32x64x128      | 2,117,962         | 0.0624                 | 75.09%                     | 74.59%                | Logit              |
| Student_48x96x256      | 6,337,194         | 0.1868                 | 78.54%                     | 77.95%                | Logit              |
| Student_16x32x64       | 530,090           | 0.0156                 | 68.56%                     | 69.00%                | Attention-Based    |
| Student_32x64x128      | 2,117,962         | 0.0624                 | 74.79%                     | 74.44%                | Attention-Based    |
| Student_48x96x256      | 6,337,194         | 0.1868                 | 77.14%                     | 76.35%                | Attention-Based    |
| Combined KD            | 2,117,962         | 0.0624                 | 78.54%                     | 75.38%                | Combined KD        |

---

## Achievements

- **Logit-Based KD**: Test accuracies ranged from **68.08% to 77.95%**.
- **Attention-Based KD**: Test accuracies ranged from **69.00% to 76.35%**.
- **Combined KD**: Achieved a test accuracy of **75.38%** with **2.1M parameters**, showing competitive performance with high compression rates.

---

## Tools and Frameworks

- **Programming Language**: Python
- **Deep Learning Framework**: PyTorch
- **Environment**: Google Colab
- **Visualization**: Matplotlib, Seaborn

---

## Future Work

- Experiment with larger and more complex datasets such as CIFAR-100 or ImageNet.
- Investigate **self-distillation** methods for further model compression and improved accuracy.

---

## How to Run the Code

1. Clone this repository:
   ```bash
   git clone <repo-url>
   cd <repo-folder>
