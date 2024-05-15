# Oxford-Flowers-102-Image-Classification
How to fine-tune a pre-trained ResNet50 model on the Oxford Flowers-102 dataset for image classification. The goal is to classify images of 102 different flower species.
Introduction
This project utilizes transfer learning, a powerful technique where a model trained on a large dataset (ImageNet in this case) is adapted to a specific task with a smaller dataset (Oxford Flowers-102). We fine-tune the ResNet50 model by adjusting its final layers to learn features specific to flower classification.

# Dataset
The Oxford Flowers-102 dataset is a challenging benchmark dataset for fine-grained visual categorization. It consists of:

102 Categories: Images of 102 different flower species.
Images: Approximately 1,000 images per class.
Splits: Predefined training, validation, and test splits.
Dependencies
To run this code, you'll need the following libraries:

TensorFlow
TensorFlow Datasets
Keras
Matplotlib
NumPy
You can install them using the following command:

pip install tensorflow tensorflow_datasets keras matplotlib numpy

Usage
Clone the Repository:

Bash
git clone <Repository-url>

Install Dependencies:

pip install -r requirements.txt 
Run the Code:
python oxford_flowers102_classification.py

(Replace oxford_flowers102_classification.py with your main Python file's name if it's different.)

# Methodology
Data Loading and Preprocessing:

Load the Oxford Flowers-102 dataset using tensorflow_datasets.
Split the data into training, validation, and test sets.
Apply data augmentation (random flipping, brightness, and contrast adjustments) to the training set.
Resize all images to (224, 224) to match ResNet50's input size.

# Model Fine-Tuning:
Load the pre-trained ResNet50 model (without the top classification layer).
Freeze the initial layers to preserve general image features.
Add custom dense layers for flower classification on top of ResNet50.
Compile the model with sparse_categorical_crossentropy loss, Adam optimizer, and accuracy metric.
Train the model using early stopping to prevent overfitting.

# Evaluation:
Evaluate the model's accuracy on the test set.
Optionally,As needed visualize predictions for a few sample images.

Results
The model achieves an accuracy of approximately 99.4 % on the test set.
