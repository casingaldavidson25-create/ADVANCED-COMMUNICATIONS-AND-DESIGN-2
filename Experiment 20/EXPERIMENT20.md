# Experiment 20: Undersampling in Software Defined Radio (SDR)

**Course:** Digital Communications  
**Lab Platform:** Emona Telecoms-Trainer 101

---

## 📖 Table of Contents
1. [Introduction to SDR](#introduction-to-sdr)
2. [Theory: The Power of Undersampling](#theory-the-power-of-undersampling)
3. [Equipment Required](#equipment-required)
4. [Part A: Modeling a DSBSC Signal](#part-a-modeling-a-dsbsc-signal)
5. [Part B: Down-conversion using Undersampling](#part-b-down-conversion-using-undersampling)
6. [Part C: Reconstructing the Message](#part-c-reconstructing-the-message)
7. [Conclusion](#conclusion)

---

## 📝 Introduction to SDR

Software Defined Radio (SDR) represents a paradigm shift in telecommunications. Traditionally, changing a radio's modulation format (from AM to FM, for example) required completely different hardware. SDR solves this by using a single flexible hardware "front-end" that digitizes signals as close to the antenna as possible, allowing all decoding and processing to happen in software.

### Figure 1: Conventional Receiver vs. SDR Block Diagram

![Image](https://github.com/user-attachments/assets/d9252d2e-0a37-4575-abcc-5df0b41e3c8e)

---

## 🔬 Theory: The Power of Undersampling

A core challenge for SDR is the high frequency of modern carriers (GHz range), which are often too fast for standard Analog-to-Digital Converters (ADCs). 

**Undersampling** (or super-Nyquist sampling) is a technique where a signal is sampled at a rate much lower than its carrier frequency, but still high enough relative to its actual bandwidth. This process utilizes the aliasing effect intentionally to "translate" or down-convert a high-frequency modulated signal to a much lower Intermediate Frequency (IF) or even directly to baseband.

---

## 🛠 Equipment Required

* **Emona Telecoms-Trainer 101**
* **Dual Channel Oscilloscope**
* **Multiplier Module** (to generate DSBSC)
* **Dual Analog Switch Module** (to act as the sampler)
* **Master Signals Module** (100kHz Sine and 2kHz Sine)
* **Tuneable Low-pass Filter Module**
* **VCO Module** (as the sampling clock)

---

## 📡 Part A: Modeling a DSBSC Signal

Before testing the SDR concept, we must generate a high-frequency modulated signal. In this experiment, we create a Double-Sideband Suppressed Carrier (DSBSC) signal by multiplying a 2kHz message with a 100kHz carrier.

### Figure 3: DSBSC Modulator Setup

![Image](https://github.com/user-attachments/assets/cf6484b0-2d60-4d57-b644-94be28de4ce0)

---

## ⚡ Part B: Down-conversion using Undersampling

In a typical SDR, the modulated carrier is sampled. If the sampling frequency is chosen correctly, one of the aliases of the sampled signal will fall within the baseband range.

### Setup Instructions
1. Use the **Dual Analog Switch** as a simple sampler.
2. The DSBSC signal from the Multiplier is fed into the switch.
3. A sampling clock (from the **VCO** or **Master Signals**) controls the switch.
4. By sampling a 100kHz carrier at a specific rate (e.g., 8.333kHz), we can effectively down-convert the signal.

---

## 🔄 Part C: Reconstructing the Message

The output of the sampler is a series of pulses (PAM signal). To recover the original 2kHz audio message, we must remove the high-frequency sampling artifacts using a filter.

### Figure 6: Complete Undersampling Receiver Wiring

![Image](https://github.com/user-attachments/assets/13b1047a-c16b-4283-9277-3e5a0407c721)

### Observations
* **Synchronicity:** Just like product detection, if the sampling clock is not perfectly synchronized with the carrier, the recovered message may exhibit "beating" or frequency errors.
* **Filter Role:** The **Tuneable Low-pass Filter** is critical for isolating the baseband alias from the other higher-frequency aliases produced by the sampling process.

---

## 🏁 Conclusion

Through this experiment, we demonstrated:
* How SDR simplifies hardware by replacing physical mixers and oscillators with sampling logic.
* The practical application of the **Aliasing** phenomenon to perform frequency down-conversion.
* The high sensitivity of undersampling systems to clock stability and synchronization.
