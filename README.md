# Automatic License Plate Recognition System (YOLOv8)

## Overview

This project implements an **Automatic Number Plate Recognition (ANPR)** system using deep learning.
The system processes a video input, detects vehicles, identifies license plates, and generates a visualized output video highlighting detected plates.

The project uses the **YOLOv8 object detection model** for vehicle detection and a trained license plate detector to identify number plates from video frames.

---

## Demo

The following demo shows how the system detects vehicles and recognizes license plates from a video stream.

---

## Project Pipeline

The system follows the pipeline below:

1. Input video is loaded.
2. Vehicles are detected using the YOLOv8 model.
3. License plates are detected within vehicle regions.
4. Vehicles are tracked across frames using the SORT tracking algorithm.
5. Detection results are stored in a CSV file.
6. Missing frame data is interpolated.
7. A final output video is generated with bounding boxes and plate numbers.

---

## Technologies Used

* Python
* OpenCV
* PyTorch
* YOLOv8
* SORT Tracking Algorithm

---

## Project Structure

```
Automatic-License-Plate-Recognition-YOLOv8
│
├── main.py
├── visualize.py
├── add_missing_data.py
├── util.py
├── requirements.txt
├── sample.mp4
├── test.csv
└── README.md
```

---

## Data

The sample video used for testing can be downloaded here:

https://drive.google.com/file/d/1JbwLyqpFCXmftaJY1oap8Sa6KfjoWJta/view

Place the downloaded file in the project root folder as:

```
sample.mp4
```

---

## Model

The project uses a pre-trained **YOLOv8 Nano (YOLOv8n)** model to detect vehicles.

A license plate detector trained using YOLOv8 is used to detect number plates.
The dataset used for training is available here:

https://universe.roboflow.com/roboflow-universe-projects/license-plate-recognition-rxg4e/dataset/4

The trained model can be downloaded from:

https://drive.google.com/file/d/1Zmf5ynaTFhmln2z7Qvv-tgjkWQYQ9Zdw/view

After downloading, place the model file in the project directory.

---

## Dependencies

The project requires the SORT tracking module.

Clone it using:

```
git clone https://github.com/abewley/sort
```

Place the `sort` folder inside the project directory.

---

## Project Setup

### 1. Clone the Repository

```
git clone https://github.com/Haider4300/Automatic-License-Plate-Recognition-YOLOv8.git
cd Automatic-License-Plate-Recognition-YOLOv8
```

---

### 2. Create a Virtual Environment

```
python -m venv env
```

---

### 3. Activate Environment

**Windows**

```
env\Scripts\activate
```

**Linux / Mac**

```
source env/bin/activate
```

---

### 4. Install Required Packages

```
pip install -r requirements.txt
```

---

## Running the Project

### Step 1 — Run the Detection Script

```
python main.py
```

This step processes the input video and generates a detection results file:

```
test.csv
```

---

### Step 2 — Interpolate Missing Frame Data

```
python add_missing_data.py
```

This script fills missing frame values and smooths tracking data.

---

### Step 3 — Generate Visualization Output

```
python visualize.py
```

After running this script, the final output video will be generated.

Output file:

```
out.mp4
```

---

## Output

The generated video (`out.mp4`) contains:

* Vehicle bounding boxes
* Detected license plates
* Vehicle tracking across frames

To open the output video in Windows Terminal:

```
start out.mp4
```

---

## Acknowledgment

This project implementation is inspired by the work of
Muhammad Zeerak Khan.

The original project provided the base structure for automatic license plate recognition using YOLOv8.

---

## License

This project is intended for educational and research purposes.
