# Hand Gesture-Based Brightness Control Using Python, OpenCV & MediaPipe

This project implements a real-time hand-gesture-controlled system for adjusting screen brightness (Brightness Up / Brightness Down) using a webcam.
The fingertip distance between the Thumb Tip and the Index Finger Tip is measured using MediaPipe Hands, and based on this distance, the system automatically triggers brightness control commands.

This project showcases how Computer Vision can be used to interact with the computer without any physical input devices, making the system simple, intuitive, and fully real-time.


# 📌 Key Features

✔ Real-time hand detection using MediaPipe Hands

✔ Tracks thumb tip & index finger tip coordinates

✔ Computes Euclidean distance

✔ Automatically triggers:

**Brightness Up when distance ≥ 51**

**Brightness Down when distance < 50**

✔ Works with Windows brightness control tools

✔ Cooldown system to prevent fast repeated actions

✔ Fast, lightweight, and easy to use

✔ No high-end hardware required

✔ Cross-platform compatibility (Windows recommended)

# 📽 How It Works

1. The webcam captures real-time video.

2. MediaPipe detects 21 hand landmarks.

3. The code extracts two important landmarks:

        Thumb Tip → Landmark 4

        Index Finger Tip → Landmark 8

4. A line is drawn between the two points, and the distance is calculated.

        If the distance is large → Brightness Up
   
        If the distance is small → Brightness Down

6. The system brightness changes based on detected gestures.

# 📦 Installation & Setup

Install dependencies manually:

        pip install opencv-python mediapipe pyautogui numpy screen-brightness-control

**(If you use Windows 10/11, brightness control works smoothly)**

# 🧠 Technologies Used

| Technology          | Purpose                          |
| ------------------- | -------------------------------- |
| **Python**          | Core programming language        |
| **OpenCV**          | Webcam capture & frame rendering |
| **MediaPipe Hands** | Hand landmark tracking           |
| **PyAutoGUI**       | Optional interaction support     |
| **NumPy**           | Distance calculation             |
| **SBC** (Windows)   | Brightness control library       |


# ⚙️ Code Explanation (High-Level)

**Hand Detection**

MediaPipe returns 21 hand landmarks.

Only two are used:

| Landmark | Finger           | Index |
| -------- | ---------------- | ----- |
| 4        | Thumb Tip        | 4     |
| 8        | Index Finger Tip | 8     |


# Distance Calculation

The Euclidean distance between thumb and index finger:

        distance = sqrt( (x2 - x1)^2 + (y2 - y1)^2 )

# Action Logic
        If distance ≥ 51 px → Brightness Up
        
        If distance < 50 px → Brightness Down

# 📊 Demo Output (On Screen)

**Green line + text → Brightness Up**

**Red line + text → Brightness Down**

The connecting line between the thumb and index fingertip changes color based on detected action.




