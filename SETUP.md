# Setup Guide

This guide explains how to set up and run the **Drone-Based Human Drowning Detection Using Image Processing** project.

---

## Important Files

| File                                          | Description                                                                               |
| --------------------------------------------- | ----------------------------------------------------------------------------------------- |
| `src/person_detection_baseline.py`            | Baseline OpenCV-based person detection script                                             |
| `config/dataset.yaml`                         | Dataset configuration file for object-detection training                                  |
| `reports/project_report.pdf`                  | Full project report with hardware, software, implementation, and testing details          |
| `reports/project_synopsis.pdf`                | Concise project synopsis                                                                  |
| `presentations/Project_Idea_Presentation.pdf` | Project presentation                                                                      |
| `assets/`                                     | Visual diagrams, prototype photos, detection screenshots, GPS output, and workflow images |
| `requirements.txt`                            | Python dependencies required to run the project                                           |

---

## 1. Clone the Repository

```
git clone https://github.com/your-username/drone-drowning-detection.git
cd drone-drowning-detection
```

Replace `your-username` with your actual GitHub username.

---

## 2. Create and Activate Virtual Environment

Create virtual environment:

```
python -m venv venv
```

Activate it:

For Windows:

```
venv\Scripts\activate
```

For macOS/Linux:

```
source venv/bin/activate
```

---

## 3. Install Dependencies

```
pip install -r requirements.txt
```

Main packages used:

```
numpy
opencv-python
matplotlib
ultralytics
PyYAML
```

---

## 4. Run the Detection Script

```
python src/person_detection_baseline.py
```

The script opens the webcam, detects people using OpenCV, draws bounding boxes, and displays the live detection window.

Press `q` to stop the program.

---

## Project Structure

```
drone-drowning-detection/
│
├── README.md
├── setup.md
├── requirements.txt
├── .gitignore
│
├── src/
│   └── person_detection_baseline.py
│
├── config/
│   └── dataset.yaml
│
├── reports/
│   ├── project_report.pdf
│   └── project_synopsis.pdf
│
├── presentations/
│   └── Project_Idea_Presentation.pdf
│
├── assets/
│   ├── drone_built.png
│   ├── drone_flight_test.png
│   ├── drone_parts_3d_printing.png
│   ├── drone_parts_3d_printing_machine.png
│   ├── drowning_detection_live.png
│   ├── drowning_detection_ouput.png
│   ├── gps_output.png
│   ├── gps_output_campus.png
│   └── system_workflow.png
│
└── outputs/
```

---

## Raspberry Pi / Ground Station Notes

* Connect the webcam or camera before running the script.
* Use VNC Viewer to access the Raspberry Pi from the ground-station laptop.
* If the webcam does not open, change the camera index in the script:

  cap = cv2.VideoCapture(1)

---

## Common Issues

| Issue                   | Fix                                                            |
| ----------------------- | -------------------------------------------------------------- |
| Webcam not opening      | Check camera connection or change camera index from `0` to `1` |
| Missing package error   | Run `pip install -r requirements.txt` again                    |
| Output video not saving | Make sure the `outputs/` folder exists                         |
| YOLO not working        | Confirm `ultralytics` is installed                             |

---

## Quick Run

```
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python src/person_detection_baseline.py
```

For Windows, use:

```
venv\Scripts\activate
```
