# Emotion Recognition

## 📌 Project Overview
This project implements an **Emotion Recognition model** using the [CREMA-D dataset](https://github.com/CheyneyComputerScience/CREMA-D) (Crowd-sourced Emotional Multimodal Actors Dataset).  
The goal is to classify human emotions from speech and visual features, extracted from audio and image files from the dataset.

### Workflow
- Data loading and preprocessing
- Feature extraction (e.g., spectrograms, HOG, LBP)
- Dimensionality reduction of Mel Spectrogram features using PCA. 
- Exploratory Data Analysis (EDA) on both audio and image modalities
- Building the classifier (Linear Regression-based classification)
- Evaluation of model performance

---

## ⚙️ Features Implemented
### Audio
First, audio is resampled to a specific sampling rate, then the features are computed. The features which I tried out are:
- Zero Crossing Rate (ZCR), root means square (RMS) of amplitude.
- **Spectrograms** - linear frequency, mel, log mel. Also, **first derivative of the log-mel** spec.
- Constant-Q Transform (**CQT**)

### Image
Image Preprocessing: Resize them, then convert into grayscale or split into RGB channels. Features tried:
- Histograms of pixel intensities.
- Local Binary Patterns (**LBP**) and **Sobel** features.
- Histogram of Oriented Gradients (**HOG**).

### Exploratory Data Analysis (EDA)
EDA is performed on both image and audio files.
- **Image file statistics** - For each type of file (.jpeg, .png, .tiff), the stats computed and used are - shape, mean, std_dev, histogram.
- **Audio file statistics** - For each type of file (.wav, .mp3, .flac), the stats computed and used are - sample rate, mean amplitude, std_dev.

### Final features used
The model was performing the best using the following features - 
- Image: **HOG, Sobel - mean and std_dev**.
- Audio: **Log_mel, mel and d1(log_mel) - mean and std_dev** for all three.
    - *Note: d1(f) - denotes the first derivative of the feature f.

---

## 📥 Dataset
The dataset can be downloaded here:  
👉 [CREMA-D Dataset](https://github.com/CheyneyComputerScience/CREMA-D)

- Official dataset contains **video files**.  
- In this project, **audio** was directly extracted and **images** were pre-extracted from video frames.  

---

## 📈 Results
(paste pics for all of these later)

### Exploratory Plots
- Histograms of grayscale intensities revealed that neutral and happy emotions had more balanced distributions, while anger and disgust emotions were skewed towards darker pixel intensities.
- Spectrogram plots showed clear differences in energy concentration across emotions (e.g., higher frequencies were more pronounced in angry speech).

### PCA Analysis
- The first 40 principal coomponents retained 

### Classification Accuracy
