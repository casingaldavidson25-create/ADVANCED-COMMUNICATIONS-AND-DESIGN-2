# Experiment 13: PCM Decoding

**Course:** Digital Communications  
**Lab Platform:** Emona Telecoms-Trainer 101

---

## 📖 Table of Contents
1. [Preliminary Discussion](#preliminary-discussion)
2. [The Decoding Process](#the-decoding-process)
3. [Equipment Required](#equipment-required)
4. [Part A: Recovering the Message from PCM Data](#part-a-recovering-the-message-from-pcm-data)
5. [Part B: Pulse Amplitude Modulation (PAM) Output](#part-b-pulse-amplitude-modulation-pam-output)
6. [Part C: Encoding and Decoding Speech](#part-c-encoding-and-decoding-speech)
7. [Conclusion](#conclusion)

---

## 📝 Preliminary Discussion

The previous experiment introduced the basics of **Pulse Code Modulation (PCM)**, which is the system for converting message signals into a continuous serial stream of binary numbers (encoding). 

This experiment focuses on **Decoding**: the process of recovering the original analog message from that serial binary stream. Successful decoding is essential for telecommunications, ensuring that the digital data received is converted back into high-quality audio or video.

### Figure 1: The PCM System Overview

![Image](https://github.com/user-attachments/assets/5b96c239-57fa-4ed9-a453-b88b4b808bc6)

---

## 🔬 The Decoding Process

At its simplest level, PCM decoding involves several critical steps:

1.  **Frame Identification:** Identifying where each new frame begins in the data stream.
2.  **Extraction:** Pulling the binary numbers from each frame.
3.  **Voltage Generation:** Creating a voltage proportional to the binary number.
4.  **Holding:** Maintaining that voltage until the next frame is decoded, creating a Pulse Amplitude Modulation (PAM) signal.
5.  **Reconstruction:** Passing the PAM signal through a Low-Pass Filter to recover the original smooth analog waveform.

---

## 🛠 Equipment Required

* **Emona Telecoms-Trainer 101** (plus power-pack)
* **Dual Channel Oscilloscope**
* **PCM Encoder & Decoder Modules**
* **Tuneable Low-pass Filter Module**
* **Speech Module**
* **Assorted Patch Leads**

---

## 📡 Part A: Recovering the Message from PCM Data

In this section, we set up the hardware to translate a 2kHz sine wave into PCM data and then back into an analog signal.

### Setup Instructions
1.  Connect the Master Signals **2kHz SINE** output to the PCM Encoder.
2.  Link the Encoder's **PCM Output** to the Decoder's **PCM Input**.
3.  Ensure the Clock and Frame Synchronization (FS) leads are properly shared between modules to maintain timing.

### Figure 3: Initial Decoding Setup

![Image](https://github.com/user-attachments/assets/dca49971-047d-4536-8d77-0a276633d593)

---

## ⚡ Part B: Pulse Amplitude Modulation (PAM) Output

Before the signal is fully reconstructed, it exists as a "staircase" waveform known as PAM. This signal contains the original message frequency along with high-frequency "switching" noise.

### Figure 5: PAM Waveform Observation

![Image](https://github.com/user-attachments/assets/ec388165-83ab-4b34-ab54-bacda7466ac9)

### Analysis
* The output of the PCM Decoder is a stepped version of the original sine wave.
* To smooth these steps, we utilize the **Tuneable Low-pass Filter**.

---

## 🗣 Part C: Encoding and Decoding Speech

The final stage of the lab moves from simple sine waves to complex human speech. This demonstrates the system's performance in real-world telecommunication scenarios.

### Figure 9: Speech Encoding/Decoding Wiring

![Image](https://github.com/user-attachments/assets/12e7e402-8592-4984-8e62-5fcfb6d9b1c2)
![Image](https://github.com/user-attachments/assets/9f7f0eb1-fa3c-4ee7-8f0e-a96509d2e7b0)

### Figure 10: Final System Integration

![Image](https://github.com/user-attachments/assets/b8de2bb6-d227-47c6-89bf-5b8128241f3c)

### Procedure
1.  Replace the sine wave input with the **Speech Module**.
2.  Monitor the output using the **Buffer Module** and headphones or the oscilloscope.
3.  Observe how the system handles the dynamic range and frequency variations of the human voice.

---

## 🏁 Conclusion

Through this experiment, we demonstrated that:
* Digital-to-Analog conversion requires precise timing (Clock and FS).
* The reconstruction filter is the final, essential step in the PCM process.
* The quality of the decoded speech is a direct result of the sampling rate and quantization levels used during the initial encoding phase.
