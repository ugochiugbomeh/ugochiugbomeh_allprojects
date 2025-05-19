# Medical Image Classification using SVM, CNN, U-Net & Transfer Learning

**Author**: Ugochiyenum Nicole Ugbomeh
**Coursework**: CW536 ( Robert Gordon Unviversity 2023/2024)
**Goal**: Classify medical X-ray images (heart vs non-heart, open vs closed valves), segment anatomical structures, 
and compare traditional ML with deep learning models including U-Net and ResNet-based transfer learning.

---

## Project Overview
This project explores classical machine learning and deep learning approaches for medical image classification and segmentation. 
It progresses from basic classifiers to more sophisticated neural architectures like U-Net and ResNet152V2.

---

## Tasks Breakdown

### Task 1: Heart vs Non-Heart Classification

* **Techniques Used**:

  * HOG Feature Extraction + SVM
  * CNN (custom-built)
  * K-Fold Cross Validation
  * SMOTE for balancing class imbalance
* **Result**: All models achieved 100% accuracy. CNN took more training time but showed better handling of image complexity.

###  Task 2: Valve Position Classification (Open vs Closed)

* **Model**: CNN
* **Result**:
  * Accuracy: **97.7%**
  * AUC-ROC: **0.98**
  * Only 1 misclassified image
* **Insight**: CNN demonstrated high sensitivity to subtle anatomical differences in valve position.

###  Task 3: Image Segmentation with U-Net & Transfer Learning

* **Models**:
  * **U-Net**: For semantic segmentation of heart X-rays and masks
  * **ResNet152V2**: Transfer learning using pre-trained weights
  * Fine-tuning ResNet for improved validation accuracy
* **Results**:
  * U-Net achieved accurate mask reconstruction for image segmentation
  * Transfer Learning Model Accuracy: **91%**, improved to **\~97%** after fine-tuning

---

##  Tools & Frameworks

* Python (Colab)
* OpenCV, Seaborn, Matplotlib
* Scikit-learn, SMOTE
* TensorFlow / Keras
* CNN, U-Net, ResNet152V2 (Transfer Learning)
* ImageDataGenerator (augmentation)

---

##  Performance Summary

| Task / Model          | Accuracy | Notes                                        |
| --------------------- | -------- | -------------------------------------------- |
| HOG + SVM             | 100%     | Fast and simple, good for low-resource cases |
| CNN (Heart/Non-Heart) | 100%     | Slower but better generalisation             |
| CNN (Open vs Closed)  | 97.7%    | High accuracy on small dataset               |
| U-Net (Segmentation)  | ✔️       | Accurate anatomical mask reconstruction      |
| ResNet152V2 (TL)      | 91%      | Improved with fine-tuning to 97%             |

---

## Real-World Applications

These models can be applied in:

* **Clinical Diagnostics**: Automating the classification of heart valve conditions, improving diagnostic speed and reliability.
* **Radiology Assistance**: U-Net can segment key anatomical areas, aiding radiologists in identifying abnormal regions.
* **Telemedicine & Mobile Health**: Lightweight SVM-HOG models can run on low-resource devices in rural clinics.
* **Medical Training**: Visualisation of CNN and U-Net outputs can enhance learning tools for anatomy and diagnostics.
* **Preoperative Assessments**: Identifying heart valve status pre-surgery with consistent accuracy.

---

## Future Work

1. **Deploy Models to the Web**: Use Streamlit, Flask or TensorFlow Lite to allow real-time classification.
2. **Introduce Vision Transformers (ViT)**: To compare transformer-based models on image classification and segmentation.
3. **Multi-Class Expansion**: Move beyond binary labels (e.g., classifying multiple heart anomalies).
4. **Model Explainability**: Integrate Grad-CAM or SHAP to visualise important regions contributing to decisions.
5. **Improve Generalisation**: Train on diverse datasets (e.g., multiple imaging modalities or hospitals).
6. **Evaluate Segmentation with Metrics**: Add IoU and Dice Coefficient scores to validate U-Net performance.
7. **Data Augmentation at Scale**: Use synthetic generation to overcome data scarcity in medical imaging.


