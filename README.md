# Sundanese Character Classification Using MobileNetV2 Transfer Learning

This repository presents a deep learning model for classifying 30 categories of Sundanese characters (*Aksara Sunda*) using MobileNetV2 transfer learning. Built with TensorFlow and Keras, the model serves as the core intelligence behind an interactive handwriting recognition platform.

## Model Performance

- **Test Accuracy:** 94.44%
- **Validation Accuracy:** ~97%
- **Loss Function:** Sparse Categorical Crossentropy
- **Optimizer:** Adam with learning rate scheduling (`ReduceLROnPlateau`)
- **Early Stopping:** Training concluded at epoch 58 to prevent overfitting

## Technology Stack

- **Deep Learning:** TensorFlow 2.15+, Keras
- **Computer Vision:** OpenCV (`cv2`)
- **Data Science:** Scikit-learn, NumPy
- **Visualization:** Matplotlib, Seaborn

## Dataset Specifications

The model was trained on a dataset sourced from Kaggle by Abdi Dwi Ramdani.

- **Total Images:** 1,800 handwritten samples
- **Input Resolution:** 128 × 128 pixels (RGB)
- **Classes:** 30 categories covering both *Ngalagena* and *Swara* characters
- **Preprocessing:** Pixel normalization to the range [0, 1] and dynamic data augmentation (rotation, zoom, and translation)

## Model Architecture

This project utilizes transfer learning with the MobileNetV2 architecture:

1. **Base Model:** MobileNetV2 pretrained on ImageNet with early layers frozen.
2. **Fine-Tuning:** The top 30 layers were unfrozen to specialize in Sundanese character stroke patterns.
3. **Custom Classification Head:**
   - Flatten Layer
   - Dense Layer (512 Units)
   - Batch Normalization
   - Dropout (0.5)

This architecture provides strong generalization while maintaining efficient inference performance.

## Repository Structure

```text
.
├── models/
│   ├── aksara_model.keras
│   ├── best_model.keras
│   ├── label_encoder.pkl
│   └── training_history.json
├── model-aksara-sunda.ipynb
└── README.md
```

## How to Use

1. Install the required dependencies:

```bash
pip install tensorflow opencv-python scikit-learn matplotlib seaborn
```

2. Open `model-aksara-sunda.ipynb` using Jupyter Notebook or Visual Studio Code, then run all cells to preprocess the dataset, train the model, and evaluate its performance.

3. The trained model and label encoder will be exported to:

```text
models/
├── aksara_model.keras
├── best_model.keras
├── label_encoder.pkl
└── training_history.json
```

4. Load the exported `.keras` model into a FastAPI backend for real-time Sundanese character prediction.


The platform provides real-time handwriting recognition and feedback through an interactive digital canvas designed to support the learning and preservation of Sundanese script.
