# Digital Communications Lab: Emona Telecoms-Trainer 101

## Introduction
This repository documents a series of advanced experiments in digital communications and telecommunications. While early experiments often focus on analog transmission, digital transmission is rapidly replacing analog in commercial applications due to its ability to resist interference caused by electrical noise.

These experiments utilize the **Emona Telecoms-Trainer 101** to explore the fundamental shift from analog signals (like speech and music) to digital data streams, covering the entire lifecycle of a signal from sampling to modulation and final reconstruction.

## Experiment Summaries

The repository covers Experiments 11 through 20, structured as follows:

### Phase 1: Digitizing Analog Signals
* **Experiment 11: Sampling and Reconstruction**
    * Explores the conversion of analog signals to digital via sampling, where the voltage is measured at regular intervals.
    * Compares "natural" sampling (where the voltage changes during measurement) with sample-and-hold schemes (fixed sample size).
    * Demonstrates message recovery using low-pass filters.

* **Experiment 12: PCM Encoding**
    * Introduces Pulse Code Modulation (PCM) to convert analog messages into a serial stream of binary numbers (0s and 1s).
    * Investigates quantization levels and the resulting quantization error caused by fitting analog voltages to specific digital levels.

* **Experiment 13: PCM Decoding**
    * Focuses on recovering the message from a serial stream by identifying frames and generating voltages proportional to the binary numbers.
    * Highlights the importance of clock synchronization and frame synchronization (FS) signals.

### Phase 2: Channel Effects and Signal Restoration
* **Experiment 14: Bandwidth Limiting and Restoring Digital Signals**
    * Models the transmission channel, demonstrating how bandwidth limiting acts as a filter, attenuating frequencies and distorting signal shapes.
    * Utilizes comparators to "restore" distorted digital signals before decoding.

### Phase 3: Digital Modulation Schemes
To share transmission channels, digital data is multiplexed using various modulation techniques:

* **Experiment 15: Amplitude Shift Keying (ASK)**
    * Implements Amplitude Shift Keying, where digital data switches a carrier's amplitude (similar to AM for digital).
    * Demonstrates demodulation using an envelope detector.

* **Experiment 16: Frequency Shift Keying (FSK)**
    * Implements FSK, switching the carrier between a "mark frequency" and a "space frequency".
    * Explores FSK's superior noise immunity compared to AM/ASK.

* **Experiment 17: Binary Phase Shift Keying (BPSK)**
    * Uses digital data to switch the carrier phase by 180 degrees.
    * Identified as a Double-Sideband Suppressed Carrier (DSBSC) scheme requiring product detection for recovery.

* **Experiment 18: Quadrature Phase Shift Keying (QPSK)**
    * An advanced DSBSC scheme that sends two bits of information at a time by using two BPSK signals phase-shifted by 90 degrees.
    * Demonstrates high spectral efficiency, allowing more users on a channel.

### Phase 4: Advanced Technologies
* **Experiment 19: DSSS Modulation and Demodulation**
    * Explores Direct Sequence Spread Spectrum (DSSS), using a pseudo-noise (PN) sequence to distribute message energy across a wide bandwidth.
    * Demonstrates the system's resistance to jamming and interference.

* **Experiment 20: Undersampling in Software Defined Radio (SDR)**
    * Introduces SDR concepts where hardware is replaced by flexible software.
    * Demonstrates "undersampling" (sampling at less than the Nyquist rate) to achieve direct down-conversion of high-frequency carrier signals.

## Hardware Used
* **Emona Telecoms-Trainer 101:** A modular telecommunications trainer.
* **Modules:** Dual Analog Switch, Master Signals, PCM Encoder/Decoder, Tuneable LPF, VCO, Multiplier, Phase Shifter, Sequence Generator, etc.
* **Measurement:** Dual Channel 20MHz Oscilloscope.
