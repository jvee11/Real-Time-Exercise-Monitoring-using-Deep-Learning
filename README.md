#  Real-Time Exercise Monitoring Using Deep Learning

This project is an AI-powered **real-time fitness exercise monitoring system** that uses **deep learning** and **computer vision** to track human body movements, count exercise repetitions, and provide posture correction from a webcam feed. It is designed to function like a personal AI trainer—lightweight, accurate, and efficient.

---

##  Features

-  **Real-Time Pose Estimation (MediaPipe / OpenPose)**
-  **Deep Learning Based Exercise Classification**
-  **Automatic Repetition Counter**
-  **Posture Correction Using Joint Angle Analysis**
-  **multiple exercises (Squats, Push-ups, Planks, Lunges, etc.)**
-  **Performance Analytics**
-  **Works with webcam or pre-recorded video**
-  **Fast and optimized for CPU**

---

##  System Architecture

Webcam / Video Feed
↓
Pose Estimation (MediaPipe / OpenPose)
↓
Keypoint Extraction (33 Landmarks)
↓
Deep Learning Classifier (LSTM/CNN/RF)
↓
Repetition Counter + Angle Analyzer
↓
Real-Time Feedback Overlay (OpenCV)

---

## Tech Stack

- **Python**
- **MediaPipe / OpenPose**
- **TensorFlow / PyTorch**
- **OpenCV**
- **Scikit-learn**
- **NumPy & Pandas**
- **Matplotlib / Seaborn**

---

## Supported Exercises

- Squats  
- Push-ups  
- Lunges  
- Planks  
- Bicep Curls  
- Shoulder Press  
- Sit-ups / Crunches  

Easily extendable to new workouts.

---


---

##  Model Details

### **Pose Estimation**
- Uses **MediaPipe BlazePose**  
- Detects **33 body landmarks**  
- Extracts `(x, y, z, visibility)` for each joint  
- Lightweight and fast for real-time use  

### **Exercise Classification**
Model Options:
- **LSTM** for sequential movement analysis  
- **1D CNN** for vector-based classification  
- **Random Forest / XGBoost** baseline  
- Uses landmark coordinates + angles  

### **Training Data**
Includes:
- Pose landmarks  
- Joint angles  
- Exercise labels  
- Multi-frame sequences  

---

##  Repetition Counting Logic

Repetition counting uses **state-based transitions**:

Example (Squats):
- **DOWN** → **UP** = 1 rep  
- Knee angle threshold controls state transitions  

Similarly:
- Push-ups = elbow angle  
- Bicep curls = arm flexion angle  
- Lunges = hip & knee angles  

---

## 📐 Posture Correction

Real-time alerts such as:
-  “Back not straight”  
-  “Knees going too forward”  
-  “Arms not fully extended”  
-  “Perfect form!”  

Works using:
- Angle deviation checks  
- Distance between joints  
- Symmetry checks  
- Model confidence score  

---

##  How to Run
installation:
  steps:
    - step: "Install Dependencies"
      command: "pip install -r requirements.txt"
    - step: "Run the Main Program"
      command: "python src/main.py"
      result: "Webcam opens and real-time exercise monitoring begins."

model_training:
  notebook: "jupyter notebook notebooks/model_training.ipynb"
  dataset_instructions: >
    Add your custom training videos inside the directory `data/raw/`.
    The system will automatically create processed training samples.

demo:
  file: "demo.mp4"
  instructions: "Replace with your demo video or GIF."

results:
  sample_results:
    - model: "LSTM"
      accuracy: "92%"
      fps: "22–30 FPS"
    - model: "CNN"
      accuracy: "88%"
      fps: "25–35 FPS"
    - model: "Random Forest"
      accuracy: "81%"
      fps: "40 FPS"
  note: "Replace these with your actual experiment results."

future_work:
  - "Add Yoga Pose Detection"
  - "Add Calorie Estimation Model"
  - "Voice-based Real-Time Feedback"
  - "Integrate with Mobile App via TensorFlow Lite"
  - "Multi-person Exercise Detection"
  - "Advanced 3D Pose Estimation"

contributing:
  message: >
    Contributions are welcome! Feel free to fork the repository,
    create issues, or submit pull requests.

license:
  type: "MIT License"
  note: "This project is open-source under the MIT License."

acknowledgements:
  - "MediaPipe BlazePose — Google AI"
  - "OpenPose — CMU Perceptual Computing Lab"
  - "TensorFlow / PyTorch"
  - "OpenCV"

 
## Screenshots

<img width="942" height="506" alt="image" src="https://github.com/user-attachments/assets/9cef2aae-f1fa-4135-a569-16a1de1c9efd" />
<img width="927" height="499" alt="image" src="https://github.com/user-attachments/assets/54cec4a3-47bb-47e1-a016-d06cde1a34c1" />

