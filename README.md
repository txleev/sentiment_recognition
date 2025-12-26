# Real-Time Emotion Detection using YOLOv8

## Project Overview
This project focuses on designing and training a deep learning model to detect human faces and classify their emotional expressions in real-time. By leveraging the **YOLOv8** architecture, the system is capable of analyzing video streams to extract sentiment insights, which has significant applications in mental health monitoring, human-computer interaction (HCI), security, and entertainment.

## Objective
The primary goal is to build an efficient object detection and classification pipeline that identifies faces and categorizes them into eight emotion classes: **Anger, Contempt, Disgust, Fear, Happy, Neutral, Sad, and Surprise**.

## Key Features
* **Real-Time Performance:** Utilizes the YOLOv8 Nano (yolov8n) variant for high-speed inference.
* **Video Analysis Pipeline:** Capability to process video files, detect faces per frame, and count emotion occurrences to interpret overall sentiment trends.
* **Custom Fine-Tuning:** Trained on facial expression datasets (AffectNet/FER2013) converted to YOLO format.

## Dataset & Preprocessing
* **Dataset Source:** Labeled facial images from AffectNet or FER2013.
* **Format:** Converted to YOLO `.txt` annotation format.
* **Preprocessing Steps:**
    * Images resized to **640x640** resolution.
    * Data augmentation applied (flipping, brightness adjustments) to mitigate dataset imbalance.
    * Dataset split into training, validation, and testing sets.

## Model Training
The model was trained using the following configuration:
* **Base Model:** YOLOv8n (Nano).
* **Epochs:** 25.
* **Batch Size:** 32.
* **Optimizer:** AdamW with a learning rate of 0.001.
* **Hardware:** NVIDIA GeForce RTX 3070.
* **Techniques:** Used Automatic Mixed Precision (AMP) and mosaic augmentation for improved efficiency and accuracy.

## Performance Metrics
The fine-tuned model achieved the following results on the validation set:
* **Precision:** 71.9%
* **Recall:** 77.5%
* **mAP@0.5:** 82.0%

### Per-Class Accuracy (mAP50)
| Emotion | mAP50 |
| :--- | :--- |
| Happy | 95.0% |
| Surprise | 84.6% |
| Fear | 84.1% |
| Contempt | 83.5% |
| Anger | 82.5% |
| Disgust | 78.4% |
| Sad | 76.8% |
| Neutral | 70.7% |

