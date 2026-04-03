# A DNN-Based Adaptive Filter for Speech Enhancement

## 1. Introduction

Speech enhancement is an important area in signal processing that focuses on improving the clarity and quality of speech signals affected by noise. In real-world environments such as traffic, crowded places, or public spaces, speech signals are often degraded, making communication difficult.

Traditional methods like Least Mean Squares (LMS), Recursive Least Squares (RLS), and Wiener filtering rely on mathematical models and often struggle in dynamic noise conditions. These methods are less effective when noise changes over time.

With the advancement of deep learning, modern approaches like Deep Neural Networks (DNNs) can learn complex relationships between noisy and clean speech signals. This project combines deep learning with adaptive filtering to achieve better performance.

The main objective is to enhance speech quality by reducing noise and improving intelligibility using a hybrid approach.

---

## 2. Methodology

### 2.1 Data Preparation
A clean speech signal is used as input. Artificial noise is added to simulate real-world noisy environments at a specific Signal-to-Noise Ratio (SNR).

Noisy Signal = Clean Speech + Noise

---

### 2.2 Feature Extraction
The speech signal is converted from the time domain to the frequency domain using Short-Time Fourier Transform (STFT). This produces a spectrogram that represents frequency variations over time.

---

### 2.3 Deep Neural Network (DNN)
A fully connected neural network is used with:
- 3 hidden layers
- 1024 neurons per layer
- ReLU activation function

The DNN learns the mapping from noisy speech to clean speech by minimizing the error between predicted and actual clean signals.

---

### 2.4 Signal Reconstruction
The predicted clean magnitude is combined with the original phase of the noisy signal and converted back into the time domain using inverse STFT.

---

### 2.5 Adaptive Filtering (Kalman Filter)
The Kalman filter is used to further refine the enhanced speech signal. It works by combining previous estimates and current measurements to produce a more accurate output.

State Update:  
x = x_prev + K * (z - x_prev)

Kalman Gain:  
K = P / (P + R)

Covariance Update:  
P = (1 - K) * P

This allows the system to adapt dynamically to changing noise conditions.

---

## 3. Pseudocode
BEGIN
load clean speech signal
add noise to create noisy signal

compute STFT of signals
Extract magnitude features 
Normalize data

initialize DNN
Train DNN using noisy and clean data 

Predict clean speech using DNN
Reconstruct signal using ISTFT

Initilize kalman filter

For each sample 
predict state 
compute kalman gain
update estimate 
update covarience 

compute SNR 
plot signals and spectrograms 
save enchaneced output

END
## 4. Results

The system was tested by adding noise to a clean speech signal at a low SNR level (around 5 dB).

### Observations:
- The noisy signal shows heavy distortion in both waveform and spectrogram.
- The DNN reduces a significant portion of the noise.
- The Kalman filter further smooths the signal and improves clarity.

### Performance:
- Input SNR: Approximately 5 dB  
- Output SNR: Significantly improved after processing  

### Outputs Generated:
- Clean, noisy, and enhanced speech waveforms  
- Spectrogram comparison plots  
- Enhanced audio file  

The results show that combining DNN with adaptive filtering produces better speech quality compared to traditional methods.

---

## 5. Conclusion

This project presents an effective speech enhancement system using a combination of deep learning and adaptive filtering. The DNN learns the characteristics of clean speech, while the Kalman filter improves real-time adaptability.

The system successfully:
- Reduces background noise  
- Improves speech clarity  
- Enhances overall audio quality  

This approach is suitable for real-world applications where noise conditions are unpredictable.

---

## 6. Limitations

- Requires a large dataset for better training  
- Computationally intensive due to deep learning  
- May not generalize well to unseen noise types  
- Phase information is not enhanced  
- Real-time implementation may introduce delay  

---

## 7. Summary

This project combines modern deep learning techniques with traditional adaptive filtering to create a robust speech enhancement system. It demonstrates how intelligent systems can improve communication quality in noisy environments.
