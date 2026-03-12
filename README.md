# Sign Language Detection using YOLOv5

## Project Overview

This project implements a **Sign Language Detection system** using the **YOLOv5 object detection model**. The goal of the system is to detect and recognize different hand gestures representing sign language words from images or video streams.

The model was trained using **Google Colab with GPU acceleration**, and the trained weights were later downloaded and integrated into a local project environment for inference.

The system currently supports detection of the following sign language gestures:

- Hello
- I Love You
- No
- Please
- Thanks
- Yes

The trained model can be used to detect these gestures in real-time or from images.

---

# Dataset Collection

The dataset used to train the model was created manually.

Images were captured using **OpenCV** to ensure that the dataset contained realistic hand gesture variations. Multiple samples of each gesture were collected under different lighting conditions and slightly different hand positions.

---

# Data Annotation

After collecting the dataset images, they were annotated using **LabelImg**.

LabelImg is a graphical image annotation tool used to create bounding boxes for object detection models. Each image was labeled by drawing bounding boxes around the hand gesture and assigning the correct class label.

The annotations were exported in **YOLO format**.

The dataset was organized into two main sets:

- Training dataset
- Validation/Test dataset

This allows the model to learn from the training images and evaluate performance on unseen images.

---

# Dataset Structure

The dataset follows the standard **YOLO dataset format**, where images and labels are stored in separate directories.

Each image has a corresponding label file containing bounding box annotations.

The dataset contains:

- Training images and labels
- Validation/Test images and labels
- A dataset configuration file describing the classes and paths

The configuration file defines:

- The number of classes
- The names of the sign language gestures
- The paths to training and validation datasets

---

# Model Training

The model was trained using **YOLOv5 in Google Colab**.

Google Colab was used because it provides free GPU access, which significantly speeds up the training process.

The training workflow included:

1. Cloning the YOLOv5 repository.
2. Installing all required dependencies.
3. Uploading the custom dataset.
4. Configuring the model to match the number of gesture classes.
5. Training the YOLOv5s model using transfer learning.

Transfer learning was used by starting from pretrained YOLOv5 weights and adapting the model to detect sign language gestures.

During training the model learned:

- Hand gesture shapes
- Gesture boundaries
- Differences between each sign

The model training process produced several outputs including training metrics, loss graphs, and trained weight files.

---

# Training Configuration

The model was trained using the **YOLOv5 Small (YOLOv5s)** architecture, which provides a good balance between accuracy and speed.

Key training parameters included:

- Image size: 416
- Batch size: 16
- Number of epochs: 300
- Pretrained weights: YOLOv5s pretrained weights
- GPU acceleration enabled in Google Colab

The model learns by minimizing three types of losses:

- Bounding box loss
- Objectness loss
- Classification loss

These losses gradually decrease during training as the model improves.

---

# Model Output

After training was completed, YOLOv5 generated the following outputs:

- Training logs
- Performance graphs
- Evaluation metrics
- Trained weight files

The most important output is the **best trained model weights file**.

This file contains the optimized neural network parameters learned during training.

---

# Local Project Setup

For running the model locally, the following steps were performed:

1. Clone the YOLOv5 repository on the local machine.
2. Install all required Python dependencies.
3. Copy the trained model weights into the project directory.
4. Run the detection script using the trained weights.


During inference, the YOLOv5 detection pipeline performs the following steps:

1. Load the trained model weights.
2. Read the input image or video frame.
3. Process the frame through the neural network.
4. Predict bounding boxes and class labels.
5. Display the detected sign language gesture.

After training and testing, the model is capable of detecting sign language gestures from images.

# Technologies Used

- Python
- YOLOv5
- PyTorch
- OpenCV
- LabelImg
- Google Colab
- CUDA GPU acceleration

---


This project demonstrates how **YOLOv5 can be used to build a custom sign language detection system**. By collecting a dataset, annotating gestures, training the model in Google Colab, and deploying the trained weights locally, a working gesture recognition pipeline can be created.

The system serves as a foundation for building more advanced **sign language interpretation systems** in the future.