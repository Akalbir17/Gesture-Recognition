# Gesture Recognition

This project aims to develop a gesture recognition system using deep learning techniques to control a smart TV without a remote. The system recognizes five different gestures performed by the user, each corresponding to a specific command.

## Table of Contents
- [Problem Statement](#problem-statement)
- [Dataset](#dataset)
  - [Dataset Structure](#dataset-structure)
  - [Data Preprocessing](#data-preprocessing)
- [Approach](#approach)
  - [Conv3D Model](#conv3d-model)
  - [Conv2D + RNN Model](#conv2d--rnn-model)
- [Results](#results)
  - [Conv3D Model](#conv3d-model-1)
  - [Conv2D + RNN Model](#conv2d--rnn-model-1)
- [Requirements](#requirements)
- [Usage](#usage)
- [License](#license)
- [Conclusion](#conclusion)

## Problem Statement
The goal is to develop a gesture recognition system for a smart TV that can recognize five different gestures performed by the user, each corresponding to a specific command:

1. Thumbs up: Increase the volume
2. Thumbs down: Decrease the volume
3. Left swipe: 'Jump' backwards 10 seconds
4. Right swipe: 'Jump' forward 10 seconds
5. Stop: Pause the movie

The gestures are continuously monitored by the webcam mounted on the TV. Each video is a sequence of 30 frames (or images).

## Dataset
The dataset consists of videos of people performing various gestures, divided into three sets: train, validation, and test.

### Dataset Structure
- The dataset is provided as a zip file containing 'train' and 'val' folders, each with a CSV file.
- Inside the 'train' and 'val' folders, there are subfolders representing videos of particular gestures.
- Each subfolder (video) contains 30 frames (images).
- The CSV file contains information about each video: the subfolder name, gesture name, and numeric label (0-4).

### Data Preprocessing
- Resized all images to a standard size of 120x120 pixels.
- Normalized pixel values between 0 and 1.
- Created data generators for training and validation sets using `ImageDataGenerator` from Keras.

## Approach
Two different approaches were used to design the gesture recognition model:
1. Conv3D
2. Conv2D + RNN (using transfer learning with MobileNet)

### Conv3D Model
- Architecture:
  - 4 Conv3D layers followed by MaxPooling3D and Dropout layers
  - Flattened output passed through Dense layers
  - ReLU activation for hidden layers, Softmax for output layer
- Compilation:
  - Loss: Categorical cross-entropy
  - Optimizer: Adam

### Conv2D + RNN Model
- Architecture:
  - MobileNet as the base model for feature extraction
  - Extracted features fed to an RNN (GRU) layer followed by Dense layers
  - ReLU activation for hidden layers, Softmax for output layer
- Compilation:
  - Loss: Categorical cross-entropy
  - Optimizer: Adam

## Results
### Conv3D Model
- Training Accuracy: 95.32%
- Validation Accuracy: 88.00%

### Conv2D + RNN Model
- Training Accuracy: 99.85%
- Validation Accuracy: 97.00%

## Requirements
- Python 3.7+
- TensorFlow 2.x
- Keras
- NumPy
- Matplotlib
- OpenCV
- Jupyter Notebook

## Usage
1. Clone the repository: git clone https://github.com/Akalbir17/gesture-recognition.git
   
2. Install the required packages: pip install -r requirements.txt

3. Open the Jupyter notebook `notebooks/Gesture_Recognition_Notebook.ipynb` and run the cells to train and evaluate the models.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Conclusion
In this project, we successfully designed a gesture recognition model using two different approaches: Conv3D and Conv2D+RNN with transfer learning (MobileNet). Both approaches performed well, with the Conv2D+RNN model achieving higher accuracy on both the training and validation sets. The models can be further improved by fine-tuning hyperparameters and using additional data augmentation techniques.

The developed gesture recognition system can be integrated into smart televisions to provide users with a convenient and intuitive way to control their TV using gestures, enhancing the overall user experience.
