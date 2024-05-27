# REAL-TIME FACIAL EMOTION DETECTION WED APPLICATION

#### Video Demo:  <URL: https://youtu.be/bWbceSZM1-s >

#### Description 

This is a real-time emotion detection web application that utilizes a pre-trained deep learning model to recognize emotions from live video feed captured by webcam.

## Overview

Emotion detection plays a crucial role in various fields, including human-computer interaction, customer feedback analysis, and mental health monitoring. This project aims to provide a user-friendly interface for real-time emotion recognition, allowing users to see their detected emotions and track emotional patterns over time.

## Features

- Real-time Video Feed: View live video feed from your webcam directly in the web browser.
- Emotion Detection: Detect and display the current emotion of the user, including anger, disgust, fear, happiness, sadness, surprise, and neutrality.
- Emotion Statistics: Track and display statistics on the occurrence of each detected emotion, providing insights into emotional patterns and trends.
- Emotion Display: Detected emotions are dynamically displayed on the web interface, providing users with immediate feedback on their emotionalstates.
- Start/Stop Controls: Users can control the video feed and emotion detection process using the intuitive start and stop buttons, providing flexibility and convenience in interacting with the application.
- Responsive Design: The web interface is designed using Bootstrap, ensuring compatibility and responsiveness across various devices and screen sizes.

## Deep Learning Model

The emotion detection model used in this project is based on deep learning and was trained on the FER-2013 dataset. FER-2013, or Facial Expression Recognition 2013, is a dataset consisting of 35,887 grayscale images of faces labeled with one of seven emotions: anger, disgust, fear, happiness, sadness, surprise, or neutrality.

## How It Works

The real-time emotion detection web application operates through the following key components and steps:

1. Web Interface:
    - The user interface is built using HTML, CSS, and Bootstrap, providing a clean and responsive design.
   - Users interact with the application through start and stop buttons to control the video feed.

2. Video Capture:
   - The application captures video from the user's webcam using the OpenCV library (`cv2.VideoCapture(0)`).
   - Frames are continuously read from the video stream for real-time processing.

3. Facial Detection:
   - OpenCV's Haar cascade classifier (`haarcascade_frontalface_default.xml`) is used to detect faces within each frame.
   - Detected faces are highlighted with bounding boxes to visually indicate the regions being analyzed.

4. Preprocessing:
   - Detected facial regions are converted to grayscale and resized to 48x48 pixels to match the input requirements of the deep learning model.
   - The preprocessed images are normalized by scaling pixel values to the range [0, 1].

5. Emotion Prediction:
   - A pre-trained deep learning model, loaded from `emotiondetector.json` and `emotiondetector.h5`(is trained from `trainmodel.ipynd`), is used to predict emotions.
   - The model takes the preprocessed facial images as input and outputs probabilities for each emotion category.
   - The emotion with the highest probability is selected as the predicted emotion.

6. Displaying Results:
   - The predicted emotion is displayed on the web interface, overlaying the bounding box of the detected face.
   - Emotion statistics are updated in real-time, showing the count of each detected emotion.

7. Start/Stop Functionality:
   - Users can start the video feed by clicking the "Start" button, which initiates the video capture and processing loop.
   - Clicking the "Stop" button pauses the video feed and clears the displayed emotions and statistics.

### Running the Application

1. Install Dependencies:
    ```bash
    pip install -r requirements.txt
    ```

2. Run the Application:
    ```bash
    python realtimedetection.py
    ```

3. Open the Web Application:
    Open your web browser and go to `http://127.0.0.1:5000/`.

## Usage

1. Start the Video Feed: Click on the **Start** button to begin the video feed and emotion detection.
2. Stop the Video Feed: Click on the **Stop** button to pause the video feed and clear the emotion detection results.

## Credits

- FER-2013 Dataset: Kaggle (https://www.kaggle.com/datasets/jonathanoheix/face-expression-recognition-dataset)
- Bootstrap CSS Framework: https://getbootstrap.com/
- OpenCV: https://opencv.org/
- Keras: https://keras.io/
