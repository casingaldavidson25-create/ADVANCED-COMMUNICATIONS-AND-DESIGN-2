# Experiment 11: Sampling and Reconstruction

## 1. Introduction
In digital communications, analog signals like speech must be converted into digital data. This starts with **sampling**, where the signal's voltage is measured at regular intervals. According to the Nyquist theorem, the sampling rate must be at least twice the highest frequency in the message to avoid aliasing. This experiment explores natural sampling (where the signal varies during the sample) and sample-and-hold (where the voltage is fixed).

## 2. Objectives
* Implement natural sampling and sample-and-hold schemes using the Emona-101.
* Observe the effect of sampling frequency on signal integrity.
* Reconstruct the original analog message using a low-pass filter.

## 3. Procedure
1. **Natural Sampling:** Connect a 2kHz sine wave to the Dual Analog Switch controlled by an 8kHz clock.
   
   **[Output Waveform: Natural Sampling]**
   *(Attach your oscilloscope screenshot here showing the message and the sampled output)*

2. **Sample-and-Hold:** Use the S/H circuit to generate a "stepped" version of the signal.
   
   **[Output Waveform: Sample-and-Hold]**
   *(Attach screenshot here)*

3. **Reconstruction:** Feed the sampled signal into a Tuneable Low-pass Filter. Adjust the cutoff frequency until the original 2kHz sine wave is recovered.

   **[Output Waveform: Reconstructed Signal]**
   *(Attach screenshot here)*

## 4. Summary of Findings
Natural sampling produces pulses that follow the message's shape, while sample-and-hold creates flat-top pulses. Reconstruction is possible as long as the sampling frequency is high enough to separate the message frequency from the sampling harmonics.

## 5. Conclusion
The experiment demonstrates that an analog signal can be successfully represented by discrete samples and reconstructed perfectly using a low-pass filter, provided the Nyquist criterion is met.
