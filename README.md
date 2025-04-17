# SMS Text Classification App

This project demonstrates a simple SMS text classification solution that uses a Linear Support Vector Classification (SVC) model to predict whether a given text message is "spam" or "not spam" (ham). A Gradio application is built to allow users to easily test text messages and receive feedback from the model.

* Sharable App Link: https://d8d43a12e63c5218f1.gradio.live (temporary)

## Overview

* Read in SMS Spam Collection csv
1.  **Define function `sms_classification`**: This function takes a Pandas DataFrame containing SMS text messages and their corresponding labels ('ham' or 'spam'). It then:
    * Splits the data into training and testing sets.
    * Creates a scikit-learn pipeline with a `TfidfVectorizer` for text feature extraction and a `LinearSVC` classifier.
    * Fits the pipeline to the training data.
    * Returns the trained pipeline model and testing scores.

2.  **Define function `sms_prediction`**: This function takes a single text message as input. It uses the pre-trained `text_clf` model to predict whether the text is spam or not and returns a user-friendly message indicating the classification.

3.  **Create Gradio application**: A `gr.Interface` is created with:
    * An input textbox where users can enter an SMS message.
    * An output textbox that displays the model's prediction ("Ham or Spam Prediction:").
4.  **Launches the Gradio app**: The application is launched, making it accessible through a web browser for users to interact with.

## Usage

Once the Gradio application is launched, a local URL will be provided. Open this URL in your web browser. You will be presented with a simple interface where you can:
* NOTE: If the app won't create the sharable link, check Windows Security Protection History and allow the app.
1.  Enter an SMS text message in the input field.
2.  The application will automatically send the text to the trained model for classification.
3.  The result, indicating whether the text is classified as "spam" or "not spam", will be displayed as feedback in the output area.

## Dependencies 

    -pandas
    -sklearn.model_selection import train_test_split
    -sklearn.pipeline import Pipeline
    -sklearn.feature_extraction.text import TfidfVectorizer
    -sklearn.svm import LinearSVC
    -gradio