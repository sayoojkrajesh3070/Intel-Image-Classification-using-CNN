# Intel Image Classification using CNN

A Deep Learning project to classify natural scenes (Buildings, Forest, Glacier, Mountain, Sea, Street) using TensorFlow and Keras.


[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sayoojkrajesh3070/Intel-Image-Classification-using-CNN/blob/main/CNN_Model.ipynb)

## 🚀 Performance
- **Test Accuracy:** ~82%
- **Model:** CNN with 3 Convolutional Layers + Dropout

## 🛠️ Built With
- Python
- TensorFlow / Keras
- Matplotlib (Visualization)
- Scikit-Learn (Metrics)

## 🧠 Technical Implementation

### Data Preprocessing & Augmentation
To ensure the model generalizes well to new images, the following techniques were used:
- **Rescaling:** Pixel values were normalized to the [0, 1] range to ensure stable gradient updates.
- **Augmentation:** Applied `RandomFlip`, `RandomRotation(0.1)`, and `RandomZoom(0.1)` layers. This prevents the model from overfitting on the specific orientation of the training images.

### CNN Architecture
The model follows a hierarchical feature extraction pattern:
1. **Convolutional Layers (3):** Used 32, 64, and 128 filters respectively. Earlier layers capture simple edges/textures, while deeper layers capture complex shapes like mountain peaks or building windows.
2. **Activation:** `ReLU` was used across all hidden layers to introduce non-linearity and avoid vanishing gradients.
3. **Regularization:** A `Dropout(0.5)` layer was added before the final output to reduce reliance on specific neurons, forcing the model to learn robust features.
4. **Output:** A `Softmax` dense layer with 6 units, providing a probability distribution across the classes.

### Training Strategy
- **Optimizer:** Adam (Adaptive Moment Estimation) for efficient learning rate management.
- **Early Stopping:** Monitored `val_loss` with a patience of 3. This ensures training stops exactly when the model begins to overfit, preserving the best possible weights.

## 📊 Results
The model successfully classifies most scenes, with high precision in identifying Forest and Buildings. The most common confusion occurs between Mountains and Glaciers due to similar visual features.

