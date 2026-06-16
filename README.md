# Handwritten Character Recognition

## Objective
Develop a deep learning model to recognize handwritten digits and characters from images.

## Dataset
MNIST Dataset (Handwritten Digits)

## Features
- Image Preprocessing
- Convolutional Neural Network (CNN)
- Handwritten Digit Classification
- High Accuracy Prediction

## Technologies Used
- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib

## Model Architecture
- Conv2D Layer
- MaxPooling2D Layer
- Flatten Layer
- Dense Layers
- Softmax Output Layer

## Project Workflow
1. Load the MNIST Dataset
2. Preprocess and Normalize Images
3. Build a CNN Model
4. Train the Model
5. Evaluate Accuracy
6. Predict Handwritten Digits

## Results
# Handwritten Character Recognition

## Objective
Develop a deep learning model to recognize handwritten digits and characters from images.

## Dataset
MNIST Dataset (Handwritten Digits)

## Features
- Image Preprocessing
- Convolutional Neural Network (CNN)
- Handwritten Digit Classification
- High Accuracy Prediction

## Technologies Used
- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib

## Model Architecture
- Conv2D Layer
- MaxPooling2D Layer
- Flatten Layer
- Dense Layers
- Softmax Output Layer

## Project Workflow
1. Load the MNIST Dataset
2. Preprocess and Normalize Images
3. Build a CNN Model
4. Train the Model
5. Evaluate Accuracy
6. Predict Handwritten Digits

## CODE

   import tensorflow as tf
from tensorflow.keras import layers, models

# Load MNIST dataset
(x_train, y_train), (x_test, y_test) = tf.keras.datasets.mnist.load_data()

# Normalize
x_train = x_train / 255.0
x_test = x_test / 255.0

# Reshape for CNN
x_train = x_train.reshape(-1, 28, 28, 1)
x_test = x_test.reshape(-1, 28, 28, 1)

# CNN Model
model = models.Sequential([
    layers.Conv2D(32, (3,3), activation='relu', input_shape=(28,28,1)),
    layers.MaxPooling2D((2,2)),
    layers.Conv2D(64, (3,3), activation='relu'),
    layers.MaxPooling2D((2,2)),
    layers.Flatten(),
    layers.Dense(128, activation='relu'),
    layers.Dense(10, activation='softmax')
])

model.compile(
    optimizer='adam',
    loss='sparse_categorical_crossentropy',
    metrics=['accuracy']
)

model.fit(x_train, y_train, epochs=5)

loss, accuracy = model.evaluate(x_test, y_test)

print("Accuracy:", accuracy)

## Results

Epoch 1/5
1875/1875 ━━━━━━━━━━━━━━━━━━━━ 31s 16ms/step - accuracy: 0.9583 - loss: 0.1338
Epoch 2/5
1875/1875 ━━━━━━━━━━━━━━━━━━━━ 41s 16ms/step - accuracy: 0.9863 - loss: 0.0443
Epoch 3/5
1875/1875 ━━━━━━━━━━━━━━━━━━━━ 30s 16ms/step - accuracy: 0.9903 - loss: 0.0301
Epoch 4/5
1875/1875 ━━━━━━━━━━━━━━━━━━━━ 42s 16ms/step - accuracy: 0.9928 - loss: 0.0222
Epoch 5/5
1875/1875 ━━━━━━━━━━━━━━━━━━━━ 30s 16ms/step - accuracy: 0.9946 - loss: 0.0166
313/313 ━━━━━━━━━━━━━━━━━━━━ 2s 6ms/step - accuracy: 0.9915 - loss: 0.0260
Accuracy: 0.9915000200271606

## Future Enhancements
- Support handwritten alphabets using EMNIST.
- Build a web application for real-time predictions.
- Extend recognition to words and sentences.

## Author
Susheel Kumar

## Internship
CodeAlpha Machine Learning Internship

## Future Enhancements
- Support handwritten alphabets using EMNIST.
- Build a web application for real-time predictions.
- Extend recognition to words and sentences.

## Author
Susheel Kumar

## Internship
CodeAlpha Machine Learning Internship
