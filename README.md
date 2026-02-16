# multi-hand-detection

---

# Hand Tracking & Gesture Recognition with MediaPipe

A robust Python-based hand detection and tracking module built using **OpenCV** and **MediaPipe**. This project features a `HandDetector` class that can identify hand landmarks, determine hand orientation (Left vs. Right), count extended fingers, and calculate distances between points in real-time.

## 🚀 Features

* **Real-time Tracking:** High-frequency hand landmark detection via MediaPipe.
* **Finger Counting:** Logic to detect which fingers are up and which are folded.
* **Hand Orientation:** Automatically distinguishes between "Left" and "Right" hands.
* **Bounding Boxes:** Automatically draws bounding boxes around detected hands.
* **Modular Design:** The `HandDetector` class can be easily imported into other computer vision projects (e.g., Virtual Painter, Gesture Volume Control).

---

## 🛠️ Installation

1. **Clone the repository:**
```bash
git clone https://github.com/your-username/hand-tracking-mediapipe.git
cd hand-tracking-mediapipe

```


2. **Install dependencies:**
Make sure you have Python 3.x installed.
```bash
pip install opencv-python mediapipe

```



---

## 💻 Usage

Run the main script to start your webcam and see the detection in action:

```bash
python your_filename.py

```

### How it Works

The project uses the 21 hand landmarks provided by MediaPipe:

* **Finger Counting:** Compares the vertical position (-coordinate) of the finger tips (IDs 8, 12, 16, 20) against their respective proximal interphalangeal joints.
* **Hand Type:** Determines if the hand is Left or Right by comparing the relative horizontal positions (-coordinate) of the pinky base (ID 17) and index base (ID 5).

---

## 📁 Project Structure

* `HandDetector`: The core class containing all processing logic.
* `findHands()`: Processes the image and draws landmarks.
* `findPosition()`: Returns a list of landmark coordinates and a bounding box.
* `fingersUp()`: Returns a list of 5 integers (0 or 1) representing the state of each finger.
* `handType()`: Identifies the hand as Left or Right.


* `main()`: A sample loop to run the detector via webcam.

---

## 📝 Configuration Parameters

In the `HandDetector` constructor, you can tweak the following:

| Parameter | Default | Description |
| --- | --- | --- |
| `mode` | `False` | Static image mode vs Video stream. |
| `maxHands` | `2` | Maximum number of hands to detect. |
| `detectionCon` | `0.5` | Minimum confidence for detection to be successful. |
| `minTrackCon` | `0.5` | Minimum confidence for tracking to be successful. |

---

## 🤝 Contributing

Feel free to fork this project, open issues, or submit pull requests. If you'd like to add gesture-based controls (like volume or cursor movement), I'd love to see them!

**Press `q` to exit the application.**

---

