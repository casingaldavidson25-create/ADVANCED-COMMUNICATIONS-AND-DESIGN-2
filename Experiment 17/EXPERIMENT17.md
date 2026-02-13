# Experiment 17: Binary Phase Shift Keying (BPSK)

**Course:** Digital Communications  
**Platform:** Emona Telecoms-Trainer 101

---

## 📖 Table of Contents
1. [Overview](#overview)
2. [Theory of BPSK](#theory-of-bpsk)
3. [Required Equipment](#required-equipment)
4. [Part A: BPSK Signal Generation](#part-a-bpsk-signal-generation)
5. [Part B: BPSK Demodulation](#part-b-bpsk-demodulation)
6. [Part C: Overcoming Phase Ambiguity](#part-c-overcoming-phase-ambiguity)
7. [Conclusion](#conclusion)

---

## 📝 Overview

While previous experiments explored Amplitude Shift Keying (ASK) and Frequency Shift Keying (FSK), this lab introduces **Binary Phase Shift Keying (BPSK)**. BPSK is a highly efficient digital modulation scheme that represents binary data by switching the phase of a carrier wave. It is widely used in wireless LANs, RFID, and satellite communications due to its robust performance in noisy environments.

---

## 🔬 Theory of BPSK

In BPSK, the phase of a constant-amplitude carrier signal is switched between two values (usually 0° and 180°) in response to a digital bitstream.

* **Binary '1':** The carrier is transmitted with a 0° phase shift.
* **Binary '0':** The carrier is transmitted with a 180° phase shift.

Mathematically, BPSK is equivalent to **Double-Sideband Suppressed Carrier (DSBSC)** modulation, where the digital data (represented as a bipolar signal) is the modulating signal. When a logic transition occurs, the carrier wave appears to "reverse direction" instantly.

---

## 🛠 Required Equipment

* **Emona Telecoms-Trainer 101**
* **Dual Channel Oscilloscope**
* **Multiplier Module** (to act as a Balanced Modulator)
* **Sequence Generator Module** (to provide the digital data)
* **Master Signals Module** (100kHz Sine)
* **Tuneable Low-pass Filter Module**

---

## 📡 Part A: BPSK Signal Generation

To create a BPSK signal, we multiply a bipolar digital signal with a continuous high-frequency carrier sine wave. The Multiplier module serves as the core of this modulator.

### Setup Instructions
1. Connect the **100kHz SINE** output from the Master Signals module to one input of the **Multiplier**.
2. Connect the **Sequence Generator** (set to PRBS) to the other input of the Multiplier.
3. Observe the output on the oscilloscope, focusing on the points where the digital data changes state; you should see a clear 180° phase reversal.

### Figure 2: BPSK Generation Wiring Diagram

![Image](https://github.com/user-attachments/assets/caf480e8-0342-4bfe-9107-9516087f54e6)

---

## ⚡ Part B: BPSK Demodulation

Demodulating a BPSK signal requires **Coherent Detection**. This means the receiver must have a local carrier that is exactly synchronized with the transmitter's carrier.

### The Demodulation Process
1. **Multiplication:** The received BPSK signal is multiplied by a local 100kHz Sine wave.
2. **Filtering:** This multiplication results in a signal containing the original digital data plus high-frequency components.
3. **Recovery:** The **Tuneable Low-pass Filter** is used to remove the high-frequency components, leaving a clean reconstruction of the original digital bitstream.

### Figure 4: BPSK Demodulator Setup

![Image](https://github.com/user-attachments/assets/8a577db4-138c-4c71-af57-947a9fb9778e)

---

## 🔄 Part C: Overcoming Phase Ambiguity

A challenge in BPSK systems is ensuring the local carrier at the receiver is in the correct phase. If the local carrier is 180° out of phase, the recovered data will be inverted (logical '1' becomes '0' and vice versa).

### Figure 6: Complete BPSK Communication System

![Image](https://github.com/user-attachments/assets/1b1bffb8-3465-4e94-8c99-a08a26a44da0)

### Observations
* By switching the phase of the local carrier, you can observe the recovered data inverting on the oscilloscope.
* In real-world systems, specialized circuits like a **Phase Locked Loop (PLL)** or **Costas Loop** are used to solve this synchronization issue.

---

## 🏁 Conclusion

Through this experiment, we successfully demonstrated:
* The generation of BPSK signals via multiplication.
* The visual identification of 180-degree phase shifts in the carrier.
* The necessity of coherent detection and low-pass filtering for accurate data recovery.
* The physical manifestation of phase ambiguity in digital communication systems.
