# Experiment 11: Sampling and Reconstruction

## 1. Introduction
The transition from analog to digital telecommunications begins with **Sampling**. This process is governed by the Nyquist-Shannon Sampling Theorem, which states that to perfectly reconstruct a signal, the sampling rate ($f_s$) must be at least twice the highest frequency component ($f_m$) of the message. 

This experiment explores the physical implementation of sampling using the Emona-101. We investigate **Natural Sampling**, where the output follows the analog signal's shape during the pulse duration, and **Sample-and-Hold (S/H)**, which creates a Pulse Amplitude Modulation (PAM) signal by maintaining a constant voltage level for the duration of the sample.



## 2. Objectives
* Demonstrate the mathematical theory of sampling using hardware modules.
* Compare the spectral differences between natural sampling and S/H sampling.
* Identify the "Aliasing" phenomenon by violating the Nyquist criterion.
* Successfully recover a 2kHz sine wave message from a pulse train.

## 3. Procedure
### Part A: Natural Sampling Setup
1. Connect the **Master Signals** 2kHz Sine wave to the input of the **Dual Analog Switch**.
2. Use the 8kHz Digital signal as the control input for the switch.
3. Observe the output on Channel 2 of the oscilloscope, triggered by the 8kHz clock.

**[Output Waveform: Natural Sampling]**
*(Space for Figure: Attach screenshot of the 2kHz sine being "chopped" by the 8kHz clock)*

### Part B: Sample-and-Hold Implementation
1. Redirect the 2kHz Sine wave through the **Sample-and-Hold** module.
2. Observe the "staircase" effect as the module holds the instantaneous voltage.

**[Output Waveform: Sample-and-Hold]**
*(Space for Figure: Attach screenshot showing the flat-topped pulses)*

### Part C: Filtering and Reconstruction
1. Connect the S/H output to the **Tuneable Low-pass Filter**.
2. Gradually increase the Cut-off Frequency. Observe how the "steps" disappear as high-frequency sampling harmonics are rejected.

**[Output Waveform: Reconstructed Signal]**
*(Space for Figure: Attach screenshot of the smoothed 2kHz sine wave)*

## 4. Summary of Findings
During the experiment, it was observed that while the sampled signal looks nothing like the original sine wave in the time domain, its frequency spectrum contains the original message. Natural sampling is easier to implement but S/H is preferred for ADC (Analog-to-Digital Converter) inputs because it provides a stable voltage for the conversion process.

## 5. Conclusion
The experiment verified that sampling is a transparent process. As long as $f_s > 2f_m$, no information is lost. The use of a Low-pass filter (Reconstruction Filter) is essential to remove the high-frequency "noise" introduced by the sampling clock, effectively returning the signal to its continuous analog form.
