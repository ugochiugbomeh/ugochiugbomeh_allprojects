## Medical Image Classification & Segmentation with SVM, CNN, U-Net and Transfer Learning
Author: Ugochiyenum Nicole Ugbomeh
Coursework: CW536 – Machine Learning for Data Science
Goal: To build, compare, and evaluate classical and deep learning models for classifying and segmenting medical X-ray images — with real-world diagnostic relevance.

## Project Overview
This project explores the use of machine learning and deep learning to detect heart-related features in medical X-rays. 
It progresses from classical feature-based models (SVM + HOG) to more advanced architectures like CNN, U-Net, and ResNet152V2. 
The pipeline includes classification (heart vs non-heart, valve open vs closed) and semantic segmentation, showcasing how AI can assist in clinical diagnosis and triage.

## Approach
Data Preparation:
- Grayscale X-rays resized and cleaned.
- HOG features extracted for classical models.
- SMOTE used to handle class imbalance.

Model Development:
- SVM trained on HOG features.
- CNN built for classification tasks.
- U-Net implemented for segmentation with masks.
- ResNet152V2 fine-tuned via transfer learning.

Evaluation:
- Accuracy, precision, recall, F1-score, and AUC used for evaluation.
- Confusion matrices and output visualisations were applied across tasks.

## Key Insights
Classical models performed exceptionally well on a small dataset
With only 1,153 images (228 heart, 925 non-heart), an SVM trained on HOG features achieved 100% accuracy, 
precision, recall, and F1-score, proving classical methods can excel with well-engineered features.

- CNNs generalised well but required more computation
A custom CNN also reached 100% test accuracy in 4 epochs, but each epoch took 40–60 seconds, compared to 0.3 seconds for SVM — highlighting the trade-off between flexibility and efficiency.

- K-Fold validation revealed potential overfitting in CNNs
Average accuracy dropped to 80.2% in 5-fold validation, with one fold at just 8.7%, indicating overfitting and sensitivity to small dataset splits.

- Heart valve classification was accurate and fast
With 218 heart-only images, the CNN achieved 97.7% accuracy and 0.984 AUC, misclassifying just one test image. Training completed in under 90 seconds.

- U-Net successfully segmented heart structures
Trained on paired X-rays and binary masks resized to 128×128, U-Net produced accurate anatomical segmentation, confirmed visually.

- Transfer learning boosted performance with fewer training samples
ResNet152V2 trained on 174 augmented RGB images reached 91% test accuracy, improving to ~97% with fine-tuning in just 15 epochs (~7 mins).

- Data imbalance was effectively handled
SMOTE balanced the 1:4 heart-to-non-heart ratio in the SVM dataset without harming performance.

- The entire pipeline is adaptable for real-world diagnostics
From preprocessing to deployment-ready models, the workflow supports mobile screening, hospital triage, and AI-assisted diagnosis.

The project successfully achieved its goal by developing and evaluating robust models for medical image classification and segmentation, 
with results that are both scientifically sound and practically applicable.

## Limitations and Future Work
The project was limited by dataset size and label scope. With only 1,153 images in the classification task and 218 for valve-state detection,
deep learning models were prone to overfitting. Segmentation was assessed visually without quantitative metrics, and classification was limited to binary labels.

Future work will include multi-class classification, quantitative segmentation metrics (Dice, IoU), 
explainability tools (Grad-CAM), and experimentation with Vision Transformers. 
The final goal is a deployable tool that supports real-time diagnosis in clinical and mobile health environments.

## Tech Stack
- Languages: Python
- Libraries: TensorFlow, Keras, scikit-learn, OpenCV, Seaborn, Matplotlib
SMOTE via imblearn
ResNet152V2 for transfer learning
U-Net for segmentation
ImageDataGenerator for augmentation


## Results Summary

| Task                   | Model         | Accuracy | Notes                                      |
|------------------------|---------------|----------|--------------------------------------------|
| Heart vs Non-Heart     | SVM (HOG)     | 100%     | Fastest, most efficient                    |
| Heart vs Non-Heart     | CNN           | 100%     | Slower, better generalisation              |
| Valve Open vs Closed   | CNN           | 97.7%    | High AUC (0.984), only 1 misclassified     |
| Heart Segmentation     | U-Net         | ✔️        | Visually validated                         |
| Classification (TL)    | ResNet152V2   | ~97%     | Fine-tuned after reaching 91% b
