#  Plant Disease Detection for Sustainable Agriculture

This project is a deep learning-based image classification system designed to detect plant diseases and recommend appropriate treatments. It uses a Convolutional Neural Network (CNN) built with TensorFlow/Keras and works with a dataset of plant leaf images.

---

##  Features

-  Automatic dataset extraction and image preprocessing
-  Custom CNN model for image classification
-  Training/Validation/Test pipeline with real-time data augmentation
-  Evaluation using Accuracy, Precision, Recall
-  Model persistence using `.keras` format
-  Visualization of training performance
-  Image inference with treatment recommendation via JSON mapping

---

> Note: This project is optimized for Google Colab and uses Google Drive for data and model storage. Adjust paths for local environments.

---

##  Dataset

Place the zipped dataset in your Google Drive:
```
/MyDrive/archive (2).zip
```

Expected extracted structure:
```
/New Plant Diseases Dataset(Augmented)/
    ├── train/
    └── valid/
```

---

##  How to Run

1. Mount Google Drive in Colab:
```python
from google.colab import drive
drive.mount('/content/drive')
```

2. Run the training pipeline from the script. Model is trained for 11 epochs.

3. Evaluate and save the trained model:
```python
model.save('PDDS.keras')
```

4. Predict diseases from test images in:
```
/content/test/test
```

And use treatment details from:
```
/content/drive/MyDrive/plant_disease_treatments.json
```

---

##  Model Overview

- 4 Conv2D layers with 32 → 256 filters
- MaxPooling and Flattening
- Dense layers with Dropout
- Output: 38-class softmax

---

##  Training Visualization

Accuracy and loss graphs for training and validation are displayed after model training.

---

##  JSON Treatment Integration

Example structure for treatment JSON:
```json
{
  "Tomato___Early_blight": {
    "class_index": 3,
    "treatment": "Use fungicides containing chlorothalonil or copper."
  }
}
```

---

##  Requirements

Install all dependencies using:

```bash
pip install -r requirements.txt
```

---











