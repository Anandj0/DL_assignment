# Neural Network Prediction for Hardness in Steel

## Overview

This repository contains a Python script for loading a pre-trained neural network model and making predictions for hardness in steel. The model is loaded using Keras, and the predictions are saved to a CSV file. Additionally, a custom loss function (`loss_MedAE`) is used during model training.

## Project Structure

- **predict_hardness.py**: Python script for loading the pre-trained model and making predictions.
- **beste_model**: Folder containing the pre-trained model file.
- **data**: Folder containing the test data and submission template.
- **README.md**: Documentation for the project.

## Getting Started

### Prerequisites

- Python 3.x
- TensorFlow
- Keras
- Pandas

### Usage

1. Clone the repository:

   bash
   git clone https://github.com/your-username/steel-hardness-prediction.git
   cd steel-hardness-prediction
   

2. Ensure that the required dependencies are installed:

   bash
   pip install tensorflow keras pandas
   

3. Run the prediction script:

   bash
   python predict_hardness.py
   

4. The predictions will be saved to a file named `S13E25_NN.csv` in the project directory.

## Loading the Pre-trained Model

The pre-trained neural network model is loaded using Keras's `load_model` function. The custom loss function `loss_MedAE` is passed as a parameter using the `custom_objects` argument.

python
from keras.models import load_model

model = load_model('beste_model', custom_objects={'loss_MedAE': loss_MedAE})


## Making Predictions

The model is then used to make predictions on the test data, and the results are saved to a CSV file.

python
result = model.predict(test_normalized) 
submission_id = submission['id'] 
prediction = pd.DataFrame(result, columns=['Hardness'], index=submission_id).to_csv('S13E25_NN.csv')


Feel free to modify the script for different use cases or experiment with the model further.



This README provides an overview of the project, instructions for usage, details about loading the pre-trained model, making predictions, and any custom functions used in the project. Adjustments can be made based on your specific project details and requirements.
