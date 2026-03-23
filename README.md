# Intel Image Classification using CNN

A Deep Learning project to classify natural scenes into six categories: Buildings, Forest, Glacier, Mountain, Sea, and Street. This project demonstrates the full machine learning pipeline, from Exploratory Data Analysis (EDA) to model evaluation on an unseen test set.

## 🚀 Performance Overview
- **Final Test Accuracy:** ~82%
- **Highest Performing Class:** Forest (F1-score: 0.94)
- **Frameworks:** TensorFlow, Keras, Scikit-Learn

## 🛠️ Technical Implementation

### 1. Data Exploration & Preprocessing
- **EDA:** Analyzed raw images to understand class distribution and image resolutions.
- **Normalization:** Pixel values rescaled to `[0, 1]` for stable training.
- **Data Augmentation:** Used `RandomFlip`, `RandomRotation`, and `RandomZoom` to increase model robustness and prevent overfitting.

### 2. CNN Architecture
The model consists of three convolutional blocks designed to capture hierarchical features:
- **Layer 1:** 32 filters (3x3) + Max Pooling.
- **Layer 2:** 64 filters (3x3) + Max Pooling.
- **Layer 3:** 128 filters (3x3) + Max Pooling.
- **Dense Head:** 128-neuron fully connected layer with **Dropout (0.5)** for regularization.
- **Output:** Softmax layer for 6-class probability distribution.

### 3. Evaluation Metrics
The model was evaluated on a dedicated **test set** (unseen data) with the following outputs:
- **Classification Report:** Detailed Precision, Recall, and F1-score per class.
- **Confusion Matrix:** Analysis of class confusion (specifically between Mountains and Glaciers).
- **Visualization:** Predicted vs. Actual labels for random samples.

## 📊 Results Visualization


The training curves indicate a healthy convergence with minimal gap between training and validation metrics, proving that the regularization techniques were effective.

## 📋 How to Run
1. Open the `CNN_Model.ipynb` in [Google Colab](https://colab.research.google.com/).
2. Run the cells sequentially to download the dataset via `kagglehub` and train the model.
3. View the final evaluation metrics at the bottom of the notebook.

## 📜 License
This project is open-source and available under the MIT License.
