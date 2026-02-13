# Experiment 19: Direct Sequence Spread Spectrum (DSSS)

**Course:** Digital Communications  
**Lab Platform:** Emona Telecoms-Trainer 101

---

## 📖 Table of Contents
1. [Preliminary Discussion](#preliminary-discussion)
2. [Theory of Spread Spectrum](#theory-of-spread-spectrum)
3. [Equipment Required](#equipment-required)
4. [Part A: Generating the DSSS Signal](#part-a-generating-the-dsss-signal)
5. [Part B: DSSS Demodulation](#part-b-bpsk-demodulation)
6. [Part C: Interference and Immunity](#part-c-interference-and-immunity)
7. [Conclusion](#conclusion)

---

## 📝 Preliminary Discussion

Direct Sequence Spread Spectrum (DSSS) is a sophisticated variation of the Double-Sideband Suppressed Carrier (DSBSC) modulation scheme. While standard DSBSC uses a simple sine wave as a carrier, DSSS uses a high-speed pulse train known as a **Pseudo-Noise (PN) sequence**.

Because a pulse train is composed of an infinite number of sine waves (fundamental and harmonics), multiplying a message by a PN sequence effectively modulates the message onto an infinite number of tiny carriers. This "spreads" the signal's energy across a very wide bandwidth, making it appear as low-level noise to unauthorized receivers.

### Figure 1: DSSS System Concept

![Image](https://github.com/user-attachments/assets/34cb7337-8573-4243-acff-5e273aeefc4b)

---

## 🔬 Theory of Spread Spectrum

The core of DSSS is the multiplication of the message signal by a much faster PN sequence.
* **Spreading:** In the frequency domain, the narrow-band message is spread into a wide-band signal.
* **Security & Robustness:** Because the power is spread so thin, the signal is difficult to jam and hard to detect without the specific PN sequence code.
* **Despreading:** At the receiver, the wide-band signal is multiplied by the *exact same* PN sequence. This "collapses" the signal back into its original narrow-band form, while any narrowband interference is spread out and filtered away.

---

## 🛠 Equipment Required

* **Emona Telecoms-Trainer 101**
* **Dual Channel Oscilloscope**
* **Multiplier Modules**
* **Sequence Generator Module** (to provide the PN sequence)
* **Master Signals Module**
* **Tuneable Low-pass Filter Module**

---

## 📡 Part A: Generating the DSSS Signal

In this stage, we implement the DSSS modulator using a Multiplier. The message (a 2kHz sine wave) is multiplied by the high-speed PN sequence from the Sequence Generator.

### Figure 3: DSSS Modulator Wiring Diagram

![Image](https://github.com/user-attachments/assets/93f19224-1d4d-4cf5-9c49-238c34073f6c)

### Figure 4: Observation of Spread Waveforms

![Image](https://github.com/user-attachments/assets/c7f3b07c-4a36-42c0-b7e3-67786ae43330)
![Image](https://github.com/user-attachments/assets/ecab6569-57e3-4802-b1a6-99ac2a18a0a5)

---

## ⚡ Part B: DSSS Demodulation

Recovery of the message requires a **Product Detector**. This involves multiplying the received DSSS signal by a "stolen" local copy of the same PN sequence used at the transmitter.

### Figure 7: DSSS Demodulation Setup

![Image](https://github.com/user-attachments/assets/e5fdd8b3-55e0-4784-8219-1b345369916d)

### Figure 8: Product Detector Integration

![Image](https://github.com/user-attachments/assets/abf16acf-5e82-47c7-a2c1-fd961205902b)

---

## 🛡 Part C: Interference and Immunity

One of the primary benefits of DSSS is its ability to reject narrowband interference (signals that occupy only a small portion of the spread bandwidth). In this section, we add an unwanted "jamming" signal to the channel to see how the despreading process naturally rejects the interference.

### Figure 10: Interference Injection Setup

![Image](https://github.com/user-attachments/assets/f8533a32-0080-4b67-82d9-ca9b71d64fe1)

### Figure 11: Final System Integration with Noise/Interference

![Image](https://github.com/user-attachments/assets/52d514ca-a812-47bb-95d6-a0ab5f59ebb8)

---

## 🏁 Conclusion

Through this experiment, we demonstrated:
* How a PN sequence spreads a message across a wide frequency spectrum.
* The requirement for precise code synchronization between the transmitter and receiver.
* The "processing gain" of DSSS, which allows a receiver to successfully recover a message even in the presence of strong narrowband interference.
