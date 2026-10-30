# Student Attentiveness Detection Using Computer Vision

A computer vision and machine learning project developed during my research internship at the National Institute of Technology Delhi (NIT Delhi).

The project explores student attentiveness detection using facial landmarks, eye-gaze information, head orientation, and eye-openness features.

**Project Status:** Research project

## Overview

The objective is to develop a system that analyzes observable facial and eye-related features to classify student attentiveness into three states:

* Attentive
* Distracted
* Sleepy

The system combines computer vision-based feature extraction with a machine learning classifier to estimate attentiveness from visual information.

## Methodology

### 1. Face Detection

OpenCV is used for image processing and face detection as part of the visual analysis pipeline.

### 2. Facial Landmark Extraction

MediaPipe Face Mesh provides facial landmarks used to derive eye-related and head-orientation features.

### 3. Feature Engineering

The model uses five features derived from visual observations:

* Iris-based gaze information.
* Head yaw.
* Head pitch.
* Eye Aspect Ratio (EAR).

The feature representation includes separate gaze coordinates and head-orientation measurements, as defined in the implementation.

### 4. Feature Scaling

Feature scaling is fitted on the training data to prevent information from the validation or test data from leaking into model training.

### 5. Classification

A multiclass Logistic Regression model predicts one of the three attentiveness categories using the extracted features.

## Technology Stack

* Python
* OpenCV
* MediaPipe Face Mesh
* NumPy
* Pandas
* scikit-learn
* Logistic Regression

## Results

The model achieved **89% accuracy** in the reported evaluation.

This figure refers to the evaluation conducted during development. Further details about the dataset, validation methodology, and per-class performance should accompany the result when available.

## Limitations

The system estimates observable visual indicators associated with attentiveness. These indicators do not directly measure a student's understanding, interest, or mental focus.

Performance may also vary with lighting, camera position, facial occlusion, and individual differences.

## Privacy Considerations

Facial imagery and derived facial features can be sensitive. Any deployment should use appropriate consent, access controls, data minimization, and retention policies.

## Future Improvements

Potential areas for further development include temporal analysis of blinking and gaze patterns, improved evaluation across different conditions, and more comprehensive privacy safeguards.

## Author

Prisha Aggarwal

Computer Engineering Student, Thapar Institute of Engineering & Technology
