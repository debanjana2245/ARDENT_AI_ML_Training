😄 Real-Time Emotion Detection System
A real-time facial emotion recognition system built with Python, OpenCV, and a custom-trained Keras deep learning model — no third-party AI APIs required.

🎯 Features

🎥 Real-time webcam-based face detection
🧠 Deep learning emotion classification using a custom .hdf5 model
😐 Detects 7 emotions: Angry, Disgust, Fear, Happy, Sad, Surprise, Neutral
🔲 Bounding box + emotion label overlay on live video feed
🍎 macOS compatible (AVFoundation backend)


🧰 Tech Stack
ComponentTechnologyLanguagePython 3Computer VisionOpenCV (cv2)Deep LearningKeras / TensorFlowFace DetectionHaar Cascade ClassifierEmotion ModelCustom trained CNN (.hdf5)

📁 Project Structure
emotion-detection/
├── emotion_detection.py               # Main application script
├── emotion_model.hdf5                 # Pre-trained Keras emotion model
├── haarcascade_frontalface_default.xml  # OpenCV face detection model
└── README.md

⚙️ Installation
1. Clone the repository
bashgit clone https://github.com/your-username/emotion-detection.git
cd emotion-detection
2. Create a virtual environment (recommended)
bashpython -m venv venv
source venv/bin/activate        # macOS/Linux
venv\Scripts\activate           # Windows
3. Install dependencies
bashpip install opencv-python numpy tensorflow keras

🚀 Usage
bashpython emotion_detection.py

A webcam window will open and begin detecting faces in real time.
Detected emotions are displayed as a label above each face bounding box.
Press q to quit the application.


🧠 How It Works

Each video frame is captured from the webcam.
The frame is converted to grayscale and scanned for faces using the Haar Cascade classifier.
Each detected face region is cropped, resized to 64×64 pixels, and normalized.
The processed image is passed through the CNN emotion model, which outputs a probability distribution across 7 emotion classes.
The highest-probability emotion is selected and rendered on the video frame.


😶 Emotion Classes
IndexEmotion0Angry1Disgust2Fear3Happy4Sad5Surprise6Neutral

📋 Requirements

Python 3.7+
Webcam / built-in camera
macOS, Windows, or Linux


⚠️ Notes

The script uses cv2.CAP_AVFOUNDATION for macOS compatibility. If you're on Windows or Linux, change the capture line in emotion_detection.py to:

python  cap = cv2.VideoCapture(0)

Ensure all three files (emotion_detection.py, emotion_model.hdf5, haarcascade_frontalface_default.xml) are in the same directory before running.


📄 License
This project is open source and available under the MIT License.
