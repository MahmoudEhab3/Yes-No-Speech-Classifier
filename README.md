# ✅ Yes-No-Speech-Classifier
This project builds a binary classifier that recognizes whether a 1-second audio clip contains the word "yes" or "no". It uses audio processing and machine learning — implementing Logistic Regression, Naive Bayes, and Ensemble Learning algorithms from scratch.

🧩 Step-by-Step Overview
## 1. Dataset: Mini Speech Commands
Audio clips from Google’s open-source dataset.

Only two classes: "yes" and "no".

1,000 samples of each, 1-second .wav files at 16 kHz.

## 2. Audio Feature Extraction
Each audio clip undergoes several preprocessing steps using the librosa library before feature extraction:

🔧 Preprocessing Steps:
Pre-emphasis filter – Reduces noise and boosts high frequencies.

Silence Removal – Trims leading and trailing silence using decibel thresholding.

Normalization – Scales audio signal amplitude between -1 and 1.

🎯 Feature Extraction:
From the cleaned audio signal, we extract the following features:

MFCCs (13 coefficients) – Represent the short-term power spectrum of sound.

Spectral Centroid – Indicates the "center of mass" of the spectrum (perceived brightness).

Spectral Rolloff – Frequency below which 85% of the signal’s energy is contained.

Zero-Crossing Rate – Measures how often the signal changes sign, useful for detecting sharp changes or noisiness.

## 3. Preprocessing
Normalized features using StandardScaler.

Balanced data using resample to avoid class bias.

Encoded labels numerically.

# 🤖 Machine Learning Models
## 1. Logistic Regression (✅ Implemented from Scratch)
Used NumPy to manually build a logistic regression classifier.

Optimized model weights using gradient descent.

Included sigmoid activation, loss calculation, and binary thresholding.

No ML libraries were used for model training.

## 2. Naive Bayes (✅ Implemented from Scratch)
Manually calculated:

Prior probabilities for each class.

Mean and variance for each feature per class.

Likelihood using the Gaussian probability density function.

Applied Bayes’ Theorem for class prediction.

## 3. Ensemble Learning (✅ Implemented from Scratch)
Implemented a simple ensemble combining:

Built-in Logistic Regression

Naive Bayes from scratch

Used majority voting for classification tasks (our case).

Boosts performance and robustness compared to a single model.

## 4. 📊 Evaluation
Used standard classification metrics to evaluate performance:

Accuracy

Precision

Recall

F1-score

These metrics helped assess how well the models distinguish "yes" from "no".

## 5. 🎤 Real-Time Voice Classification
To demonstrate our model in action:

Recorded user voice using a built-in audio recording library.

Processed and classified the clip using:

Logistic Regression (from scratch)

Naive Bayes (from scratch)

Ensemble model

Output: Predicted label — "yes" or "no".

This real-time demo showcases practical use in voice-command systems, proving the models work outside of static datasets.
