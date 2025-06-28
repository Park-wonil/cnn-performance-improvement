# CNN Performance Improvement on CIFAR-10
Improving image classification accuracy by tuning CNN architecture, applying regularization techniques, optimizer changes, and data augmentation.

##  Project Overview
This project aims to improve the performance of a Convolutional Neural Network (CNN) model for image classification using the CIFAR-10 dataset. Several techniques were applied, including:

- CNN architecture enhancement (Conv & FC layers)
- Activation function experiments (ReLU → LeakyReLU → ELU)
- Regularization (Dropout, L2)
- Optimizer changes (SGD → Adam)
- Data augmentation (RandomHorizontalFlip)

---

## Dataset
- **CIFAR-10**: 60,000 32x32 color images in 10 classes, with 6,000 images per class.

---

## Techniques Applied

###  Model Architecture
- 3 convolutional layers (Conv → Conv → Conv)
- 2 fully connected (FC) layers
- Dropout layer (tested 0.3 / 0.5 / 0.7)

### Activation Functions
- ReLU → LeakyReLU → ELU (ELU dropped due to accuracy drop)

### Regularization
- Dropout: Best performance at **Dropout(0.3)**
- L2 regularization: Minor effect on test accuracy

### Optimizers
- **SGD → Adam**
- Learning rate: 0.01 → 0.001 (important for convergence)
- RMSprop tested (performance dropped)

### Data Augmentation
- `RandomCrop` removed (negative effect)
- `RandomHorizontalFlip` only → improved accuracy and stability

---

## 📊 Experimental Results Summary

| Technique Applied       | Effect on Accuracy                  |
|-------------------------|-------------------------------------|
| Conv layer expansion    | Accuracy increased                  |
| FC layer expansion      | Better feature abstraction          |
| LeakyReLU activation    | Improved training stability         |
| ELU activation          | Accuracy dropped (~2%)             |
| Dropout(0.3)            | **Highest test accuracy: 76.78%**   |
| Adam with lr=0.001      | Stable convergence                  |
| HorizontalFlip only     | Prevented overfitting, stable train |

---

## 🧪 Final Conclusion

> The best performing combination:
- **Optimizer**: Adam (lr=0.001)  
- **Dropout**: 0.3  
- **Activation**: LeakyReLU  
- **Data Augmentation**: HorizontalFlip only  
- **Test Accuracy Achieved**: **76.78%**
