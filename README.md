## Description

This project focuses on enhancing speech signals that are affected by background noise. It uses a Deep Neural Network (DNN) to learn how clean speech should sound and a Kalman adaptive filter to refine the output in real time. The system improves speech clarity, reduces noise, and increases the overall Signal-to-Noise Ratio (SNR), making the audio easier to understand.

---

## Installation

To run this project, you need Python and the following libraries installed:

- numpy  
- librosa  
- matplotlib  
- torch (PyTorch)  
- soundfile  

You can install them using pip or any Python environment manager. Make sure your environment supports audio processing and machine learning libraries.

---

## Usage

1. Place your clean speech file (`clean_speech.wav`) in the working directory.  
2. Run the Python script or Jupyter Notebook.  
3. The system will:
   - Add noise to the input signal  
   - Train the DNN model  
   - Enhance the speech signal  
   - Apply Kalman filtering  
4. The output will include:
   - Enhanced audio file  
   - Waveform plots  
   - Spectrograms  
   - SNR improvement values  

---

## Contributing

Contributions are welcome! You can improve this project by:
- Adding support for multiple noise types  
- Improving the neural network architecture (CNN, LSTM, etc.)  
- Optimizing performance for real-time applications  
- Enhancing visualization and analysis  

Feel free to fork the repository, make changes, and submit a pull request.

---

## License

This project is intended for academic and educational purposes. You are free to use, modify, and distribute it with proper credit to the original author.
