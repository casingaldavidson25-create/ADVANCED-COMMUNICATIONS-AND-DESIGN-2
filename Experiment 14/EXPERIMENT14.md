# Experiment 14: Bandwidth Limiting and Restoring Digital Signals

**Course:** Digital Communications  
**Lab Platform:** Emona Telecoms-Trainer 101

---

## 📖 Table of Contents
1. [Introduction](#introduction)
2. [Theory: Bandwidth and Digital Signals](#theory-bandwidth-and-digital-signals)
3. [Equipment Required](#equipment-required)
4. [Part A: Effects of Bandwidth Limiting](#part-a-effects-of-bandwidth-limiting)
5. [Part B: Pulse Shaping and Distortion](#part-b-pulse-shaping-and-distortion)
6. [Part C: Restoring Digital Signals](#part-c-restoring-digital-signals)
7. [Conclusion](#conclusion)

---

## 📝 Introduction

In any communication model, the message moves from a transmitter to a receiver over a channel (such as copper wire, fiber optics, or airwaves). Every medium has a finite **bandwidth**, meaning it only allows a specific range of frequencies to pass. This experiment explores how these bandwidth constraints affect digital signals and how we can restore a signal that has been distorted by the channel.

---

## 🔬 Theory: Bandwidth and Digital Signals

Digital signals, such as square waves, are composed of a fundamental frequency and an infinite series of odd harmonics. 

* **Distortion:** If a channel's bandwidth is too narrow, higher-frequency harmonics are lost. This changes the shape of the digital pulses, making them "rounded" or spread out.
* **Intersymbol Interference (ISI):** When pulses spread into the time slots of adjacent bits, it becomes difficult for the receiver to distinguish between a '0' and a '1'.
* **Restoration:** To fix this, we use a **Comparator** at the receiver end to act as a "hard-limiter," squaring up the edges of the rounded signal back into a clean digital format.

---

## 🛠 Equipment Required

* **Emona Telecoms-Trainer 101**
* **Dual Channel Oscilloscope**
* **Sequence Generator Module**
* **Tuneable Low-pass Filter Module** (Acting as the Channel)
* **Comparator Module**
* **VCO Module** (used as a variable clock)

---

## 📡 Part A: Effects of Bandwidth Limiting

In this section, we observe how a digital bit stream is affected as it passes through a channel with a shrinking bandwidth.

### Figure 3: Initial Test Setup with Sequence Generator

![Image](https://github.com/user-attachments/assets/a3584d06-0b49-4a99-9906-26b37031c774)

### Procedure
1. Generate a Pseudo-random Binary Sequence (PRBS).
2. Pass the signal through the Tuneable Low-pass Filter.
3. Observe the output as you slowly decrease the filter's cut-off frequency.

### Figure 5: Waveform Comparison (Input vs. Bandwidth Limited Output)

![Image](https://github.com/user-attachments/assets/584883e8-b7bd-41a1-b25d-ade1e9b2e6a6)

---

## ⚡ Part B: Pulse Shaping and Distortion

As the bandwidth decreases further, the "square" pulses begin to look like sine waves or triangular waves. 

### Figure 7: Heavy Bandwidth Limiting Observations

![Image](https://github.com/user-attachments/assets/4eb6a065-aeea-43c0-8542-f2ace9f1b22f)

### Figure 8: Detailed Distortion at Low Cut-off Frequencies

![Image](https://github.com/user-attachments/assets/173a1383-a68a-4ef4-a503-bec938b2039e)

---

## 🔄 Part C: Restoring Digital Signals

Once a signal is distorted, it can no longer drive digital logic gates directly. We use a Comparator to restore the signal to its original binary state.

### Setup Instructions
1. Connect the distorted output of the Filter to the input of the **Comparator**.
2. Set a reference voltage (typically 0V or a DC level) for the Comparator.
3. Compare the restored signal to the original source from the Sequence Generator.

### Figure 11: Restoration Circuitry and Comparator Connections

![Image](https://github.com/user-attachments/assets/950debe4-0aa2-42eb-ba87-b85ca323947f)
![Image](https://github.com/user-attachments/assets/3c2d1e84-a131-4859-8848-45b95cf63784)

### Figure 13: Final Restored Pulse Waveforms

![Image](https://github.com/user-attachments/assets/8f911122-c176-4d24-b7b2-dda94dbd5725)
![Image](https://github.com/user-attachments/assets/3a445c25-6fcf-4e9d-ae79-006ed6d3cc17)

---

## 🏁 Conclusion

Through this experiment, we confirmed that:
* Channels act as filters that remove high-frequency components of digital signals.
* Narrow bandwidth leads to pulse rounding and potential data loss.
* The **Comparator** is an effective tool for restoring the digital "square" shape, provided the noise floor and ISI are within manageable limits.
