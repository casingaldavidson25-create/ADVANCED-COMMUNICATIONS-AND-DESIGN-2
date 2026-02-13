# Experiment 16: Frequency Shift Keying (FSK)

**Course:** Digital Communications  
**Lab Platform:** Emona Telecoms-Trainer 101

---

## 📖 Table of Contents
1. [Preliminary Discussion](#preliminary-discussion)
2. [Theory of FSK](#theory-of-fsk)
3. [Equipment Required](#equipment-required)
4. [Part A: Generating an FSK Signal](#part-a-generating-an-fsk-signal)
5. [Part B: FSK Demodulation](#part-b-fsk-demodulation)
6. [Part C: Restoring Data with a Comparator](#part-c-restoring-data-with-a-comparator)
7. [Conclusion](#conclusion)

---

## 📝 Preliminary Discussion

Frequency Division Multiplexing (FDM) allows a communication channel to be shared among multiple users by superimposing messages onto carrier signals within allocated frequency spectrums. When Frequency Modulation (FM) is used to transmit digital data, it is known as **Binary Frequency Shift Keying (BFSK)** or simply **FSK**.

A major advantage of FSK is its relative immunity to noise compared to Amplitude Shift Keying (ASK). Because noise typically affects a signal's amplitude, FSK receivers can use "limiters" to remove amplitude variations without losing the frequency-encoded digital information.

---

## 🔬 Theory of FSK

In FSK, the carrier signal switches between two distinct frequencies based on the logic level of the digital message:
* **Mark Frequency:** The higher frequency, representing a logic high (1).
* **Space Frequency:** The lower frequency, representing a logic low (0).

Mathematically, the FSK signal can be viewed as the addition of two gated sine waves of different frequencies that are out of phase with each other's "on" time.

---

## 🛠 Equipment Required

* **Emona Telecoms-Trainer 101**
* **Dual Channel Oscilloscope**
* **Voltage Controlled Oscillator (VCO) Module**
* **Sequence Generator Module**
* **Dual Analog Switch Module**
* **Baseband Low-Pass Filter (LPF) Module**
* **Utilities Module (Comparator & Rectifier)**

---

## 📡 Part A: Generating an FSK Signal

The generation of FSK requires two different carrier frequencies. In this lab, we use the VCO and the Master Signals module to provide these carriers, which are then switched by the digital data.

### Setup Instructions
1. Connect a digital signal (from the Sequence Generator) to the control input of the **Dual Analog Switch**.
2. Feed a **100kHz Sine** wave into one switch input and a lower frequency sine wave into the other.
3. The switch will select between these two frequencies based on the digital bitstream.

### Figure 2: FSK Generation Setup

![Image](https://github.com/user-attachments/assets/1c7e90ac-db91-4e8a-9de0-160c22ce1baa)

---

## ⚡ Part B: FSK Demodulation

Demodulation is the process of extracting the original binary sequence from the frequency-shifted carrier. This experiment utilizes an envelope detection method involving a rectifier and a specialized filter.

### The Demodulation Process
Because FSK uses digital data, a filter that is highly responsive to digital transitions is required. We use the **Baseband LPF** which differs from standard RC filters used in analog AM experiments.

### Figure 4: FSK Demodulation Wiring

![Image](https://github.com/user-attachments/assets/04e88514-4c55-4d03-b4ec-2e612234319a)

---

## 🔄 Part C: Restoring Data with a Comparator

The demodulated signal often suffers from distortion and rounding due to the filtering process. To return the signal to a clean digital state suitable for logic circuits, we use a **Comparator**.

### Restoration Logic
The Comparator compares the "rounded" demodulated signal against a DC reference voltage. When the signal exceeds the reference, the output jumps to a logic high; when it falls below, it returns to a logic low.

### Figure 7: Complete System Integration (Generation to Restoration)

![Image](https://github.com/user-attachments/assets/c44addf1-d3fd-49a8-ba41-9732833177e2)

### Figure 8: Final Restoration Circuitry Connections

![Image](https://github.com/user-attachments/assets/df1c0611-50aa-46e7-be0a-f9539a22f7cf)

---

## 🏁 Conclusion

In this experiment, we successfully:
* Implemented a Frequency Shift Keying modulator using analog switches.
* Demonstrated that FSK represents data through frequency transitions rather than amplitude changes.
* Used a Baseband Low-pass Filter and a Comparator to accurately reconstruct the original digital bitstream from the modulated carrier.
