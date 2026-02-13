# Experiment 18: Quadrature Phase Shift Keying (QPSK)

**Course:** Digital Communications  
**Lab Platform:** Emona Telecoms-Trainer 101

---

## 📖 Table of Contents
1. [Introduction](#introduction)
2. [Theory of QPSK](#theory-of-qpsk)
3. [Equipment Required](#equipment-required)
4. [Part A: The Serial-to-Parallel Converter](#part-a-the-serial-to-parallel-converter)
5. [Part B: Generating the In-phase (I) and Quadrature (Q) Signals](#part-b-generating-the-in-phase-i-and-quadrature-q-signals)
6. [Part C: Generating the QPSK Signal](#part-c-generating-the-qpsk-signal)
7. [Conclusion](#conclusion)

---

## 📝 Introduction

As its name implies, **Quadrature Phase Shift Keying (QPSK)** is a variation of Binary Phase Shift Keying (BPSK). While BPSK sends digital information one bit at a time, QPSK sends two bits of digital information simultaneously without requiring additional carrier frequencies. 

The primary advantage of QPSK is spectral efficiency; by halving the data bit rate required for transmission, it requires only half the radio-frequency spectrum compared to BPSK, allowing more users to occupy the same channel.

---

## 🔬 Theory of QPSK

QPSK is achieved by splitting a serial bitstream into two parallel streams:
* **In-phase (I) Stream:** Consisting of the odd-numbered bits.
* **Quadrature (Q) Stream:** Consisting of the even-numbered bits.

These two streams are used to modulate two carriers of the same frequency that are 90° out of phase (Sine and Cosine). The resulting signals are then added together to form the final QPSK signal.

---

## 🛠 Equipment Required

* **Emona Telecoms-Trainer 101**
* **Dual Channel Oscilloscope**
* **Sequence Generator Module**
* **2-bit Serial-to-Parallel Converter Module**
* **Multiplier Modules**
* **Adder Module**
* **Master Signals Module** (100kHz Sine and Cosine)

---

## 📡 Part A: The Serial-to-Parallel Converter

The first step in QPSK generation is converting the serial data from the Sequence Generator into two parallel streams. This is handled by the **2-bit Serial-to-Parallel Converter** module.

### Setup Instructions
1. Connect the **Sequence Generator** output to the Data input of the Serial-to-Parallel Converter.
2. Synchronize the clocks of both modules to ensure accurate bit splitting.
3. Observe the relationship between the input clock and the X1/X2 outputs.

### Figure 3: Serial-to-Parallel Converter Wiring

![Image](https://github.com/user-attachments/assets/8dd0a37a-8410-44df-b417-5e08f1332d50)

---

## ⚡ Part B: Generating the I and Q Signals

Once the bits are split, each stream must be modulated onto its respective carrier. The "I" stream is multiplied with a Sine wave, and the "Q" stream is multiplied with a Cosine wave.

### Figure 5: Modulating the I and Q Components

![Image](https://github.com/user-attachments/assets/4f8b6268-1d24-4ec7-850e-fcef490f7ed0)
![Image](https://github.com/user-attachments/assets/792ad98f-d2da-4765-a0d5-4930ece76bcb)

### Analysis
* The output of each multiplier is effectively a BPSK signal.
* Because the carriers are 90° apart, these two BPSK signals are in "quadrature."

---

## 🔄 Part C: Generating the QPSK Signal

The final QPSK signal is produced by combining the I and Q modulated signals using an **Adder** module.

### Setup Instructions
1. Take the output of the "I" Multiplier and the "Q" Multiplier and connect them to the **Adder** inputs.
2. Monitor the final output on the oscilloscope.
3. Use the scope's trigger and horizontal position controls to examine the phase transitions.

### Figure 7: Complete QPSK Modulator Setup

![Image](https://github.com/user-attachments/assets/7598dcb5-dcfe-4e47-bc82-2b9368d25f27)

### Figure 9: Final System Integration and Signal Observation

![Image](https://github.com/user-attachments/assets/12d9b5cb-572f-4799-a0fb-e8f0510d1bad)
---

## 🏁 Conclusion

Through this experiment, we demonstrated the physical implementation of QPSK. Key takeaways include:
* The role of the **Serial-to-Parallel Converter** in reducing the effective bit rate for transmission.
* The use of **Quadrature Carriers** (Sine and Cosine) to transmit two bits of information in the same frequency space.
* The visual characteristics of the QPSK waveform, which contains four distinct phase states representing the bit pairs 00, 01, 10, and 11.
