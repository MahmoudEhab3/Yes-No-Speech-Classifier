# Yes-No-Speech-Classifier
This project builds a binary classifier that recognizes whether a 1-second audio clip contains the word "yes" or "no". It uses audio processing and machine learning, and importantly,implementing both Naive Bayes and Ensemble Learning algorithms from scratch.

🧩 Step-by-Step Overview
1. Dataset: Mini Speech Commands
Audio clips from Google’s dataset.

Only two classes: "yes" and "no".

1,000 samples of each, 1-second WAV files at 16 kHz.

2. Audio Feature Extraction
Each audio clip undergoes several preprocessing steps using the librosa library before feature extraction:

Preprocessing Steps:
Pre-emphasis filter – Reduces noise and boosts high frequencies.

Silence Removal – Trims leading and trailing silence using decibel thresholding.

Normalization – Scales audio signal amplitude between -1 and 1.

Feature Extraction:
From the cleaned audio signal, you extract the following features:

MFCCs (13 coefficients) – Represent the short-term power spectrum of sound.

Spectral Centroid – Indicates the "center of mass" of the spectrum (perceived brightness).

Spectral Rolloff – Frequency below which 85% of the signal’s energy is contained.

Zero-Crossing Rate – Measures how often the audio signal changes sign, useful for detecting sharp changes or noisiness.

3. Preprocessing
Normalized features using StandardScaler.

Balanced data using resample to avoid class bias.

Encoded labels numerically.

Machine Learning Models 
1. Naive Bayes (Implemented from Scratch)
manually calculated:

Prior probabilities for each class.

Mean and variance for each feature per class.

Likelihood using the Gaussian probability density function.

Then applied Bayes' Theorem to predict the class.

2. Ensemble Learning
implemented a simple ensemble method combining:

Built in Logistic Regression

Naive Bayes from scratch 

The ensemble combines predictions using Majority voting in classification tasks and averaging in regression tasks
in our case (a binary classification problem), we're using majority voting to combine model predictions.

This boosts performance and robustness compared to a single model.

📊 Evaluation
Used standard classification metrics:

Accuracy

Precision

Recall

F1-score

These helped measure how good the models are at distinguishing "yes" from "no". 

🎤 Real-Time Voice Classification
To demonstrate our model in action, we added a final step where you can:

Record your own voice using a built-in audio recording library.

Classified the audio clip with our trained models (Logistic Regression, Naive Bayes, Ensemble).

Output the predicted label: "yes" or "no".

This real-time demo showcases how the model can be used in actual voice-command applications and not just on static datasets.





