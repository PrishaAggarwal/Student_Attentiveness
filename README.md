# Student Attentiveness Detection Using Computer Vision

A computer vision and machine learning project developed during my research internship at the National Institute of Technology Delhi (NIT Delhi).

The project explores student attentiveness classification using eye-gaze information, head orientation, and eye-openness features extracted from video frames.

**Project Status:** Research project

## Overview

The objective is to investigate whether observable facial and eye-related features can help classify student attentiveness into three categories:

* Attentive
* Distracted
* Sleepy

The pipeline combines facial landmark analysis, feature engineering, and machine learning-based classification.

## Methodology

### 1. Video Input

OpenCV captures frames from a webcam or processes a prerecorded video.

### 2. Face Detection

OpenCV's Haar Cascade classifier is used to locate face regions in video frames.

### 3. Facial Landmark Detection

MediaPipe Face Mesh is used to identify facial landmarks required for gaze estimation, eye-openness analysis, and head-pose estimation.

### 4. Feature Extraction

Five features form the intended classifier input:

| Feature | Description                                 |
| ------- | ------------------------------------------- |
| GazeX   | Horizontal gaze-related coordinate          |
| GazeY   | Vertical gaze-related coordinate            |
| Yaw     | Left-right head rotation                    |
| Pitch   | Up-down head rotation                       |
| EAR     | Eye Aspect Ratio, representing eye openness |

Gaze features are derived from normalized iris positions, while head orientation is estimated using facial landmarks and a pose-estimation approach.

EAR is calculated from the geometric relationships between eye landmarks.

### 5. Feature Preprocessing

The five features have different numerical ranges. A preprocessing pipeline is therefore required before classification.

The scaler must be fitted on the training data and then applied to the test data to avoid data leakage.

### 6. Classification

A multiclass Logistic Regression classifier is used to predict one of the three attentiveness categories.

### 7. Evaluation

The intended evaluation includes:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion matrix

Performance should be reported using the actual results obtained from the final evaluation.

## Technology Stack

* Python
* OpenCV
* MediaPipe
* NumPy
* Pandas
* scikit-learn

## Limitations

Observable facial features do not directly measure learning, comprehension, or mental attention.

Results may vary with lighting, camera placement, facial occlusion, individual differences, and the quality of the training data.

A low EAR in a single frame should not automatically be interpreted as sleepiness; temporal information may be needed to distinguish a blink from sustained eye closure.

## Privacy Considerations

Facial imagery and facial measurements can be sensitive. Any deployment should use appropriate consent, access controls, data minimization, and retention policies.

Raw classroom recordings and restricted research datasets should not be published in this repository.

## Research Status

This repository documents the project's methodology and implementation as permitted for public release.

The reported performance, supported features, and execution instructions should be updated to match the verified implementation.

## Author

Prisha Aggarwal

Computer Engineering Student, Thapar Institute of Engineering & Technology
