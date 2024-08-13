
Had enough of one of my dogs raiding my trash can. Its time to catch the bandit

**Project Trash Bandit** is an automated monitoring system designed to detect which of your dogs is raiding the garbage can. The system uses a Raspberry Pi 4, a camera module, and machine learning to identify specific dogs and notify you via SMS when a breach occurs.

## Table of Contents

- [Features](#features)
- [Components](#components)
- [Installation](#installation)
- [Setup](#setup)
- [Usage](#usage)
- [Training the Model](#training-the-model)
- [License](#license)

## Features

- **Motion Detection:** Uses a PIR sensor to detect movement near the garbage can.
- **Image Capture:** Captures images using a Raspberry Pi Camera Module when motion is detected.
- **Dog Identification:** Utilizes a TensorFlow Lite model to identify which dog is present.
- **Notification System:** Sends an SMS alert with the detected dog's name using Twilio.

## Components

- Raspberry Pi 4 Model B
- Raspberry Pi Camera Module V2
- HC-SR501 PIR Motion Sensor
- MicroSD Card (32GB or higher)
- USB-C Power Supply
- Twilio Account (for SMS notifications)

## Installation

1. **Prepare the Raspberry Pi:**
   - Install Raspberry Pi OS on the microSD card using the Raspberry Pi Imager.
   - Connect the Raspberry Pi to a monitor, keyboard, and mouse for initial setup.

2. **Install Required Software:**
   - Update and upgrade your system:
     ```bash
     sudo apt update
     sudo apt upgrade
     ```
   - Install OpenCV and TensorFlow Lite:
     ```bash
     sudo apt install python3-opencv
     pip install tflite-runtime
     ```

3. **Set Up Twilio:**
   - Sign up for a Twilio account and get your account SID, authentication token, and a Twilio phone number.

## Setup

1. **Connect the Camera:**
   - Attach the Raspberry Pi Camera Module to the CSI port.

2. **Connect the PIR Sensor:**
   - Connect the PIR sensor to the Raspberry Pi GPIO pins:
     - VCC to 5V
     - GND to Ground
     - OUT to GPIO 4 (or any other available GPIO pin)

3. **Place the Raspberry Pi:**
   - Position the Raspberry Pi near the garbage can with a clear view for the camera.

## Usage

1. **Run the Detection Script:**
   - Use the following command to start the monitoring script:
     ```bash
     python3 trash_bandit_detector.py
     ```

2. **Script Operation:**
   - The script will monitor for motion and capture images when detected.
   - It will process the images to identify the dog and send a notification if a dog is detected.

## Training the Model

1. **Data Collection:**
   - Capture and label images of each dog in various conditions and poses.

2. **Model Training:**
   - Train a model using Google Teachable Machine or TensorFlow to classify images by dog name.

3. **Export to TensorFlow Lite:**
   - Export the trained model to a TensorFlow Lite format and save it as `dog_identifier_model.tflite`.

4. **Deploy Model:**
   - Transfer the model to your Raspberry Pi and place it in the project directory.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

