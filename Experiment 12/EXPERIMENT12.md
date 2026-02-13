# Experiment 11: Sampling and Reconstruction

**Course:** Telecommunications Engineering  
**Lab Platform:** Emona Telecoms-Trainer 101  

---

## 📋 Table of Contents
1. [Introduction](#introduction)
2. [Theory of Sampling](#theory-of-sampling)
3. [Equipment Required](#equipment-required)
4. [Part A: Natural Sampling](#part-a-natural-sampling)
5. [Part B: Sample-and-Hold (PAM)](#part-b-sample-and-hold-pam)
6. [Part C: Sampling Speech](#part-c-sampling-speech)
7. [Part D: Reconstruction via Low-Pass Filter](#part-d-reconstruction-via-low-pass-filter)

---

## 📝 Introduction

This experiment explores the fundamental process of converting analog signals into a format suitable for digital transmission. In modern communications, digital signals are preferred due to their high resistance to electrical noise and interference. The core of this transition is **Sampling**.

---

## 🔬 Theory of Sampling

Sampling is the process of measuring the voltage of an analog signal at regular intervals. Mathematically, it is the multiplication of an analog message by a sampling pulse train.

### Natural Sampling
In Natural Sampling, the pulse follows the amplitude of the analog signal for the duration of the sampling pulse. The sampled signal's "tops" retain the shape of the original message.

### Sample-and-Hold
In this method, the signal level is captured at a specific instant and held constant until the next sample is taken. This results in a "staircase" or "stepped" appearance, which is essential for many digital encoding systems like PCM.

---

## 🛠 Equipment Required

* **Emona Telecoms-Trainer 101**
* **Dual Channel Oscilloscope**
* **Patch Leads**
* **Master Signals Module**
* **Speech Module**
* **Tuneable Low-pass Filter Module**

---

## 📡 Part A: Natural Sampling

The initial setup involves using a 2kHz Sine wave as the message and an 8kHz Digital signal as the sampling clock.

### Setup Instructions
1. Connect the **2kHz SINE** output to the input of the **Dual Analog Switch**.
2. Connect the **8kHz DIGITAL** output to the control input of the switch.
3. Observe the output on Channel 2 of the oscilloscope.

### Block Diagram Output
![Image](https://github.com/user-attachments/assets/bb0a2932-7027-465a-8834-02a26d81094f)


---

## ⚡ Part B: Sample-and-Hold (PAM)

By modifying the switch configuration, we transition from Natural Sampling to a Sample-and-Hold scheme. This removes the "gaps" between samples and holds the voltage steady between clock pulses.

### Observation
* The signal no longer returns to zero between samples.
* The waveform appears as a series of flat-topped steps.

---

## 🗣 Part C: Sampling Speech

In this section, the static sine wave is replaced with a dynamic speech signal to simulate real-world telecommunication.

### Setup Instructions
1. Disconnect the 2kHz Sine wave.
2. Connect the **Speech Module** output to the Analog Switch input.
3. Adjust the Oscilloscope Timebase to **2ms/div** to observe the complex patterns of human speech being sampled.

### Wiring Diagram Output
![Image](https://github.com/user-attachments/assets/3a8510ca-415d-4fcc-a9f2-ec30b4cb68d9)


---

## 🔄 Part D: Reconstruction via Low-Pass Filter

To recover the original message from the sampled "pulses," the signal must be filtered. A Low-Pass Filter (LPF) is used to remove the high-frequency harmonics created by the sampling process, leaving only the original message frequency.

### Procedure
1. Feed the sampled output into the **Tuneable Low-pass Filter**.
2. Set the Filter Gain to the middle position.
3. Slowly turn the **Cut-off Frequency Adjust** clockwise until the original 2kHz Sine wave is clearly reconstructed on the oscilloscope.

### Results
* **Reconstructed Signal:** A smooth sine wave.
* **Filter Role:** Acts as an integrator to "smooth out" the steps of the sampled signal.

---

## 🏁 Conclusion

Through this experiment, the Nyquist criterion and the physical implementation of sampling were demonstrated. We successfully sampled simple and complex signals and proved that a message can be perfectly reconstructed using a simple Low-Pass Filter, provided the sampling rate is sufficient.
