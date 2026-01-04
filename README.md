# ⚽ YOLOv8 Custom Object Detection – Training & Prediction Pipeline

This project demonstrates **end-to-end custom object detection using YOLOv8**, including dataset preparation, train–validation split, model training, and prediction on images and videos. The workflow is implemented using **Python and Ultralytics YOLOv8** in a Jupyter/Google Colab environment.
The project starts by installing required libraries and preparing the dataset in YOLO format. A custom Python function is used to split the dataset into training and validation sets. The YOLOv8 Small model (`yolov8s.pt`) is then fine-tuned on a custom dataset (football player detection) using a YAML configuration file. Finally, predictions are performed on both images and videos using the trained model.
Technologies used include Python, Ultralytics YOLOv8, OpenCV  (backend), tqdm for progress visualization, and Google Drive for dataset and result storage.

Project Structure:
Yolov8/
│
├── data/                         # Raw dataset (images + labels)
├── yolo_data/
│   ├── images/
│   │   ├── train/                # Training images
│   │   └── val/                  # Validation images
│   ├── labels/
│   │   ├── train/                # Training labels (.txt)
│   │   └── val/                  # Validation labels (.txt)
│
├── test_images/                  # Images for prediction
├── vid2/
│   └── test_video1.mp4           # Video for prediction
├── dataset.yaml                  # YOLO dataset configuration file
├── training_results/
│   └── footballplayer/
│       └── weights/
│           └── best.pt            # Trained model weights
└── README.md

Requirements:
- Python 3.x
- ultralytics
- tqdm
- opencv-python
- Google Colab or Jupyter Notebook (recommended)

Installation:
pip install ultralytics  
pip install tqdm --upgrade  

Dataset Preparation:
A custom Python function is used to randomly split the dataset into training and validation sets (80% train, 20% validation). Images and corresponding label files are automatically copied into YOLO-compatible directory structures.

Model Training:
The YOLOv8 Small model is trained using the following configuration:
- Task: Object Detection
- Model: yolov8s.pt
- Epochs: 10
- Batch Size: 8
- Dataset: dataset.yaml
- Output Directory: training_results/footballplayer

Prediction:
- Image prediction is performed on a folder containing test images.
- Video prediction is performed on a single video file.
- Confidence threshold is set to 0.40.
- The trained model (`best.pt`) is used for inference.

Results & Outputs:
- 🔗 Trained Image Annotations (Train Output): [https://drive.google.com/drive/u/0/folders/1JGTSilMIoTe-ip4q9ZD4OXYf5KoNuZue]
- 🔗 Test Image Predictions: [https://drive.google.com/drive/u/0/folders/1RPy41JBdOvCBUYOpGASqSQTZVPOX9zWf]
- 🔗 Video Prediction Output: [https://drive.google.com/drive/u/0/folders/1CtBZA4LhAsutNdSZQWA6q9RInGJMXZ_J]

Applications:
- Sports analytics and player detection  
- Custom object detection projects  
- Computer vision research and learning  
- Real-time image and video analysis  
- AI-based surveillance and monitoring systems  

Future Enhancements:
- Increase epochs and dataset size for better accuracy  
- Train on larger YOLOv8 variants (m/l/x)  
- Integrate object tracking (ByteTrack / DeepSORT)  
- Export results to JSON/CSV  
- Deploy as a web or mobile application  
- Optimize model for edge devices  

