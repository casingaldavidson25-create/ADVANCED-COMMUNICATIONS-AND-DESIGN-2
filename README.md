# Digital Communications Lab: Emona Telecoms-Trainer 101

## Introduction
This repository documents a series of advanced experiments in digital communications and telecommunications. [cite_start]While early experiments often focus on analog transmission, digital transmission is rapidly replacing analog in commercial applications due to its ability to resist interference caused by electrical noise[cite: 7, 8].

These experiments utilize the **Emona Telecoms-Trainer 101** to explore the fundamental shift from analog signals (like speech and music) to digital data streams, covering the entire lifecycle of a signal from sampling to modulation and final reconstruction.

## Experiment Summaries

The repository covers Experiments 11 through 20, structured as follows:

### Phase 1: Digitizing Analog Signals
* **Experiment 11: Sampling and Reconstruction**
    * [cite_start]Explores the conversion of analog signals to digital via sampling, where the voltage is measured at regular intervals[cite: 11].
    * [cite_start]Compares "natural" sampling (where the voltage changes during measurement) with sample-and-hold schemes (fixed sample size)[cite: 14, 16].
    * [cite_start]Demonstrates message recovery using low-pass filters[cite: 38].

* **Experiment 12: PCM Encoding**
    * [cite_start]Introduces Pulse Code Modulation (PCM) to convert analog messages into a serial stream of binary numbers (0s and 1s)[cite: 201].
    * [cite_start]Investigates quantization levels and the resulting quantization error caused by fitting analog voltages to specific digital levels[cite: 204, 214].

* **Experiment 13: PCM Decoding**
    * [cite_start]Focuses on recovering the message from a serial stream by identifying frames and generating voltages proportional to the binary numbers[cite: 437, 441].
    * [cite_start]Highlights the importance of clock synchronization and frame synchronization (FS) signals[cite: 444, 451].

### Phase 2: Channel Effects and Signal Restoration
* **Experiment 14: Bandwidth Limiting and Restoring Digital Signals**
    * [cite_start]Models the transmission channel, demonstrating how bandwidth limiting acts as a filter, attenuating frequencies and distorting signal shapes[cite: 697, 698].
    * [cite_start]Utilizes comparators to "restore" distorted digital signals before decoding[cite: 720].

### Phase 3: Digital Modulation Schemes
To share transmission channels, digital data is multiplexed using various modulation techniques:

* **Experiment 15: Amplitude Shift Keying (ASK)**
    * [cite_start]Implements Amplitude Shift Keying, where digital data switches a carrier's amplitude (similar to AM for digital)[cite: 961].
    * [cite_start]Demonstrates demodulation using an envelope detector[cite: 979].

* **Experiment 16: Frequency Shift Keying (FSK)**
    * [cite_start]Implements FSK, switching the carrier between a "mark frequency" and a "space frequency"[cite: 1166, 1168].
    * [cite_start]Explores FSK's superior noise immunity compared to AM/ASK[cite: 1160].

* **Experiment 17: Binary Phase Shift Keying (BPSK)**
    * [cite_start]Uses digital data to switch the carrier phase by 180 degrees[cite: 1381, 1386].
    * [cite_start]Identified as a Double-Sideband Suppressed Carrier (DSBSC) scheme requiring product detection for recovery[cite: 1388].

* **Experiment 18: Quadrature Phase Shift Keying (QPSK)**
    * [cite_start]An advanced DSBSC scheme that sends two bits of information at a time by using two BPSK signals phase-shifted by 90 degrees[cite: 1614, 1638].
    * [cite_start]Demonstrates high spectral efficiency, allowing more users on a channel[cite: 1619].

### Phase 4: Advanced Technologies
* **Experiment 19: DSSS Modulation and Demodulation**
    * [cite_start]Explores Direct Sequence Spread Spectrum (DSSS), using a pseudo-noise (PN) sequence to distribute message energy across a wide bandwidth[cite: 1888, 1911].
    * [cite_start]Demonstrates the system's resistance to jamming and interference[cite: 1893].

* **Experiment 20: Undersampling in Software Defined Radio (SDR)**
    * [cite_start]Introduces SDR concepts where hardware is replaced by flexible software[cite: 2108].
    * [cite_start]Demonstrates "undersampling" (sampling at less than the Nyquist rate) to achieve direct down-conversion of high-frequency carrier signals[cite: 2126, 2129].

## Hardware Used
* **Emona Telecoms-Trainer 101:** A modular telecommunications trainer.
* **Modules:** Dual Analog Switch, Master Signals, PCM Encoder/Decoder, Tuneable LPF, VCO, Multiplier, Phase Shifter, Sequence Generator, etc.
* **Measurement:** Dual Channel 20MHz Oscilloscope.
