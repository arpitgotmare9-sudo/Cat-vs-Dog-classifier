# Cat vs. Dog Classification using CNN

A binary image classification project built using TensorFlow and Keras to distinguish between cats and dogs using a Convolutional Neural Network (CNN).

The model is trained on 25,000 images and uses convolutional layers to extract visual features and classify images into two categories.

## Overview

The objective of this project is to understand how Convolutional Neural Networks work in image classification and implement a complete training pipeline, from data preprocessing to prediction on unseen images.

The model consists of three convolutional blocks followed by fully connected layers. It uses batch normalization and dropout to support training and reduce overfitting.

## Dataset

The dataset was obtained from Kaggle.

**Dataset:** [Dogs vs. Cats – Kaggle](https://www.kaggle.com/datasets/salader/dogsvscats)

| Split | Number of Images |
|---|---:|
| Training | 20,000 |
| Validation | 5,000 |
| Total | 25,000 |

All images are resized to 256 × 256 pixels and normalized to the range [0, 1] before training.

## Model Architecture

The CNN consists of three convolutional blocks, each containing a convolutional layer, batch normalization, and max pooling.

The extracted features are passed through fully connected layers before the final binary classification.

```text
Input Image (256 × 256 × 3)
          |
Conv2D (32 filters, 3 × 3)
          |
Batch Normalization
          |
Max Pooling (2 × 2)
          |
Conv2D (64 filters, 3 × 3)
          |
Batch Normalization
          |
Max Pooling (2 × 2)
          |
Conv2D (128 filters, 3 × 3)
          |
Batch Normalization
          |
Max Pooling (2 × 2)
          |
Flatten
          |
Dense (128, ReLU)
          |
Dropout (0.1)
          |
Dense (64, ReLU)
          |
Dropout (0.1)
          |
Dense (1, Sigmoid)
          |
Cat / Dog
```

### Model Configuration

| Parameter | Value |
|---|---|
| Framework | TensorFlow / Keras |
| Input Shape | 256 × 256 × 3 |
| Optimizer | Adam |
| Loss Function | Binary Crossentropy |
| Batch Size | 32 |
| Epochs | 10 |
| Output Activation | Sigmoid |

## Results

The model was trained for 10 epochs and evaluated on the validation dataset.

| Metric | Result |
|---|---:|
| Training Accuracy | 97.71% |
| Validation Accuracy | 81.36% |
| Training Loss | 0.0680 |
| Validation Loss | 0.6653 |

The difference between training and validation performance indicates that the model is overfitting. Although it learns the training data effectively, its performance on unseen images is lower.

## Prediction

The model takes an image as input, resizes it to 256 × 256 pixels, normalizes the pixel values, and generates a prediction using the sigmoid output.

The classification threshold is 0.5:

- Output below 0.5: Cat
- Output greater than or equal to 0.5: Dog

Example:

```text
Raw Prediction Value: 0.0001558
Prediction: Cat
```

## Technologies Used

- Python
- TensorFlow and Keras
- OpenCV
- NumPy
- Matplotlib
- Google Colab

## How to Run

The project was developed and trained using Google Colab.

1. Open the notebook in Google Colab.
2. Download the dataset from Kaggle.
3. Extract the dataset into the required directory structure.
4. Run the preprocessing and model-building cells.
5. Train the model.
6. Load an image and run the prediction cell.

For local execution, install the required dependencies:

```bash
pip install tensorflow opencv-python matplotlib numpy
```

## Key Learnings

- Implementing a CNN for binary image classification.
- Understanding convolution, pooling, and fully connected layers.
- Preprocessing and normalizing image data.
- Training and evaluating a neural network using TensorFlow and Keras.
- Identifying overfitting through training and validation metrics.
- Making predictions on new images.

## Future Improvements

- Apply data augmentation to improve generalization.
- Use early stopping to reduce overfitting.
- Experiment with transfer learning using pretrained models.
- Improve validation performance.
- Deploy the trained model through a simple web application.

## Author

**Arpit Gotmare**

B.Tech Engineering Student | Artificial Intelligence
