# Raspberry Pi 2-Factor Authentication Security System

This project is a comprehensive security system built on a Raspberry Pi that requires two-factor authentication (2FA) to grant access. It uses both facial recognition and a keypad password to control a servo-driven lock mechanism, providing a robust and modern security solution while being completely offline


## Features

Dual-Factor Authentication: Access is only granted when an authorized face is detected and the correct password is entered on the keypad.

Live Facial Recognition: Uses a Pi Camera and the face_recognition library to perform real-time face detection and identification.

Physical Lock Control: A servo motor simulates a physical lock, moving to an "unlocked" position upon successful authentication.

Visual Feedback: On-screen bounding boxes identify detected faces, and red/green LEDs provide a clear visual status of the system (locked/unlocked).

Interactive Keypad: A 4x4 matrix keypad allows for secure password entry, including keys for submitting (#) and clearing (*) the input.
## Hardware

Raspberry Pi, model 3B+ with at least 8GB of ram for the model

Raspberry Pi Camera Module

Servo Motor

4x4 Matrix Keypad

1x Red LED

1x Green LED

Breadboard and Jumper Wires
## Setup
Firstly, create a virtual enviornment within your Raspberry PI and configure your IDE of your choice to utilise that enviornment after all libraries are installed.
Ensure you have all the required Python libraries. Install them by running the following commands one by one in your terminal:

- pip install opencv-python
- pip install numpy
- pip install imutils
- pip install face_recognition
- pip install gpiozero
- pip install pad4pi
- pip install picamera2


## Train the model

- Before running the main script, you need to train the system to recognize authorized faces.

- use the image capture code to take pictures and automatically upload the code to a file accessible to the main code

- Run the encode_faces.py script (the training script you provided earlier). This will generate an encodings.pickle file, which the main program needs.
## Usage

- Make sure your encodings.pickle file is in the same directory as the script.

- Run the main script from the terminal:

- python facial_keypad_lock.py

- A window will appear showing the live camera feed. The red LED will be on, indicating the system is locked.

- To unlock, an authorized person must be clearly visible to the camera. While their face is detected, enter the correct password on the keypad and press the # key to submit.

- If both conditions are met, the green LED will turn on, and the servo will move to the "unlocked" position for 5 seconds before re-locking.

- To quit the program, click on the video window and press the 'q' key.

- CREDIT TO CORE ELECTRONICS FOR MODEL CODE
