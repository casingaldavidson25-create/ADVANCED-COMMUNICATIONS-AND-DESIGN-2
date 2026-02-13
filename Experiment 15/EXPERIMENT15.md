# Experiment 15: Amplitude Shift Keying (ASK)

**Course:** Digital Communications  
**Lab Platform:** Emona Telecoms-Trainer 101

---

## 📖 Table of Contents
1. [Preliminary Discussion](#preliminary-discussion)
2. [Theory: Amplitude Shift Keying](#theory-amplitude-shift-keying)
3. [Equipment Required](#equipment-required)
4. [Part A: Generating an ASK Signal](#part-a-generating-an-ask-signal)
5. [Part B: Demodulating an ASK Signal](#part-b-demodulating-an-ask-signal)
6. [Part C: Signal Restoration](#part-c-signal-restoration)
7. [Conclusion](#conclusion)

---

## 📝 Preliminary Discussion

A fundamental requirement in modern telecommunications is the ability to share a single channel (copper, fiber, or airwaves) among multiple users. Without sharing, only one person could transmit at a time, making systems like mobile networks or television broadcasting impossible.

One method of sharing is **Frequency Division Multiplexing (FDM)**. This requires shifting baseband digital signals to higher frequencies using a process called **Modulation**. In digital communications, one of the simplest forms of this is **Amplitude Shift Keying (ASK)**.

---

## 🔬 Theory: Amplitude Shift Keying

ASK is a form of modulation that represents digital data as variations in the amplitude of a carrier wave. 

* **Binary '1':** The carrier signal is transmitted at its full amplitude.
* **Binary '0':** The carrier signal is reduced to zero amplitude (switched off).

Essentially, ASK is a product of a digital signal (the message) and a high-frequency sine wave (the carrier). This is why it is often referred to as "On-Off Keying."

---

## 🛠 Equipment Required

* **Emona Telecoms-Trainer 101**
* **Dual Channel Oscilloscope**
* **Sequence Generator Module**
* **Master Signals Module (100kHz Sine)**
* **Dual Analog Switch Module**
* **Tuneable Low-pass Filter Module**
* **Utilities Module (Rectifier)**

---

## 📡 Part A: Generating an ASK Signal

To generate an ASK signal, we use a digital bit stream to control a switch that either allows or blocks a high-frequency carrier wave.

### Setup Instructions
1. Connect a **2kHz DIGITAL** signal (or a PRBS) to the control input of the **Dual Analog Switch**.
2. Connect a **100kHz SINE** wave to the input of the switch.
3. Observe the output on the oscilloscope to see the carrier wave appearing and disappearing in sync with the digital bits.

### Figure 2: ASK Generation Wiring Diagram

![Image](https://github.com/user-attachments/assets/6908421b-b8c9-457b-bfbc-3d78ff252039)

---

## ⚡ Part B: Demodulating an ASK Signal

Demodulation is the process of recovering the original digital data from the modulated carrier. For ASK, this is commonly done using an **Envelope Detector**.

### The Envelope Detection Process
1. **Rectification:** The ASK signal is passed through a diode (rectifier) to remove the negative half of the carrier wave.
2. **Filtering:** A Low-Pass Filter (LPF) is used to "smooth out" the remaining high-frequency carrier pulses, leaving behind the envelope of the signal, which matches the original digital data.

### Figure 4: ASK Demodulation via Rectifier and Filter

![Image](https://github.com/user-attachments/assets/1d09e820-1d64-4653-b28c-0626ee72305b)

---

## 🔄 Part C: Signal Restoration

In real-world scenarios, the recovered signal from the envelope detector is often "rounded" or noisy due to the filtering process. To make the signal compatible with digital logic, a restoration step is required.

### Figure 6: Complete System Wiring (Generation to Recovery)

![Image](https://github.com/user-attachments/assets/afb7f3d6-7886-4070-bab4-040d3cac7ac0)

### Figure 8: Detailed Observation of Recovered vs. Original Data

![Image](https://github.com/user-attachments/assets/e7333570-c7c1-4417-8d82-d7af1fdde366)

### Analysis
* The **Tuneable Low-pass Filter** cut-off frequency must be carefully adjusted. If the bandwidth is too narrow, the digital pulses become overly rounded.
* A **Comparator** (not shown in all diagrams but utilized in advanced setups) can be used to "square up" the recovered signal, returning it to a clean 0V or 5V logic level.

---

## 🏁 Conclusion

Through this experiment, we demonstrated:
* The physical implementation of ASK using a high-frequency carrier and a digital switch.
* The effectiveness of envelope detection (Rectification + LPF) in recovering digital intelligence.
* The importance of bandwidth management in maintaining the integrity of the recovered bitstream.
