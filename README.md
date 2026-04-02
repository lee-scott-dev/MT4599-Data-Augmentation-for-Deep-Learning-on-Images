# BSc Dissertation – Data Augmentation for Skin Lesion Classification

**Graded 92/100 | Highly Commended | University of St Andrews**

A multi-model comparative study (full paper available on request) evaluating the impact of four data augmentation strategies on CNN-based binary classification of pigmented skin lesions (typical vs atypical) from the HAM10000 dermatoscopic dataset (10,015 images).

## Overview

This project designed and executed an end-to-end study training 8 CNN models - pairing two architectures (LeNet-5 and EfficientNetV2-B0) with four augmentation strategies:

1. **No augmentation** (baseline)
2. **Manual warping** (rotation, flip, zoom, brightness)
3. **Grid-search optimised warping** (automated parameter selection)
4. **DCGAN-based oversampling** (synthetic minority-class image generation)

### Key Results
- Best model (EfficientNetV2-B0 + manual augmentation) achieved **~90% accuracy** and **F1 ~89%** on unseen test data
- Data augmentation improved metrics across all architectures
- DCGAN successfully generated synthetic lesion images to address the 2:1 class imbalance

### Techniques
- Transfer learning (EfficientNetV2-B0 pretrained on ImageNet)
- DCGAN implementation and training for synthetic image generation
- Early stopping, callbacks, and dropout regularisation
- AUC-ROC, confusion matrix, and misclassification trend analysis across lesion type and body localisation

## Tech Stack
- Python, TensorFlow, Keras
- NumPy, pandas, matplotlib, seaborn
- Jupyter Notebook

## Dataset
[HAM10000](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000) - 10,015 dermatoscopic images across 7 lesion categories, reduced to binary classification (melanocytic nevi vs all others).

## Related
- [Skin Lesion Inference API](https://github.com/lee-scott-dev/skin-lesion-api) - FastAPI service deploying models from this dissertation
