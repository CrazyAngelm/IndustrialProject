# Technical Research on Smart Speaker Development: Audio Solutions

The aim of this study is to explore audio solutions in the context of smart speaker development. We will examine the technical parameters and configurations of microphones.

The choice of a microphone in the context of smart speaker development is crucial for the initial reception of the audio signal. At this stage, artifacts and unwanted noises can be eliminated, allowing for high-quality signal processing later on. When selecting a microphone, it is important to consider parameters such as sensitivity, signal-to-noise ratio (SNR), and frequency range.

### Microphone Parameters

**Dynamic Range** – the difference between the quietest and loudest sound that a microphone can capture, measured in dB SPL.

$$
DR = 20log_{10}(\frac{P_{max}}{P_{min}})
$$

The dynamic range of normal human speech is between 60 and 70 dB SPL. A lower sensitivity level may result in speech being unrecognized if it falls below the sensitivity threshold, or it may blend with background noise, which is particularly relevant in office environments. An excessively high dynamic range can overload the microphone, creating artifacts due to spectrum clipping by DSP algorithms. In both cases, amplifiers and compressors (either physical or software-based) can be used.

**Microphone sensitivity** is a parameter that indicates how well it converts sound pressure (SPL) into an electrical signal. The higher the sensitivity, the stronger the output signal for the same sound level. It is measured in mV/Pa: 10 mV/Pa means that the microphone outputs 10 mV at a sound pressure of 1 Pa (94 dB SPL). For convenience, this unit is often expressed in dB.

$$
Sensitivity(dB) = 20 * log_{10}(\frac{Sensitivity(mV/Pa)}{1000})
$$

Microphones with high sensitivity can capture quieter speech, but they also pick up background noise and may overload from soft speech. On the other hand, lower sensitivity is more resistant to noise but may fail to capture fragments of speech. The optimal sensitivity range is between -40 to -30 dB.

**SNR (Signal-to-Noise Ratio)** - describes the strength of the signal relative to the noise and unwanted sounds. The higher this parameter, the clearer the speech input. It is measured in dB. A 30 dB SNR means the useful signal is 1000 times stronger than the noise. An SNR value between 40 dB and 60 dB is considered normal for recognizing human speech.

**The frequency response** describes the range of sound frequencies that the microphone can capture without significant distortion, measured in Hz. The components essential for speech intelligibility lie within the range of 100 Hz to 8 kHz. It is important to note that, unlike English, Russian speech is characterized by a greater presence of "hissing" and "whistling" sounds, which fall within the 4-8 kHz range.

| **Frequency**  | **Sounds** | **The importance of frequency response** |
| --- | --- | --- |
| **80-250 Hz** | Bass and sub-bass frequencies, depth of voice | Not significant |
| **250-500 Hz** | Vowels like "A", "O", "U", "Y"  | Significant |
| **500-2000 Hz** | Fundamental harmonics of speech, key consonants | Critical |
| **2000-4000 Hz** | Clarity of pronunciation, consonants "T", "K", "P", "F” | Significant |
| **4000-8000 Hz** | Hissing and whistling sounds ("SH", "SCH", "ZH", "TS", "S", "Z") | Significant |
| **8000-12000 Hz** | Airiness, detailing | Not significant |

### **Comparison table of main microphone parameters**

| **Parameter** | **What it affects** | **The characteristic of the parameter** | **The optimal value for human speech** |
| --- | --- | --- | --- |
| **Dynamic Range**  | It determines how wide a range of volumes the microphone can capture – from the quietest to the loudest sounds without distortion. | It concerns not only weak sounds but also loud ones, preventing overload.

 | 80–120 dB |
| **Sensitivity** | It affects the microphone's ability to capture quiet sounds. The higher the sensitivity, the more faint sounds are captured. | How loud the output signal will be at the same input sound level.

 | -50 до -35 dB/Pa |
| **SNR** | It affects the clarity of the recording: the higher the SNR, the less noise in the signal. | SNR evaluates how well the useful signal is separated from background noise. | 60–70 dB |
| **Frequency response**  | It determines which frequencies the microphone can capture (low, mid, high). It affects the fullness and naturalness of the sound. | It does not concern the volume level and is not related to noise. | 100 Hz – 8 kHz |

### Condenser microphone

Sound vibrations alter the capacitance of the condenser, forming an electrical signal. This type is characterized by high sensitivity (-40 dB to -20 dB), a wide frequency range (20 Hz to 20 kHz), a high signal-to-noise ratio (SNR) (70-85 dB), a broad dynamic range (120 dB SPL), and low distortion. However, a condenser microphone requires phantom power and is sensitive to humidity.

Notably, these microphones are widely used in studio and live performance settings due to their precise sound reproduction, especially in the high and mid-frequency ranges. They are also utilized in measurement technology, broadcasting, and professional audio recording.

### Electret microphone

The operating principle is similar to that of a condenser microphone but does not require phantom power, as the charged electret material inside the microphone creates a constant electric field. Electret microphones are compact, inexpensive, and easy to connect. Their frequency range is 50 Hz – 16 kHz, sensitivity is -40 dB ±3 dB, signal-to-noise ratio (SNR) is 90-100 dB SPL, and operating voltage is 1.5 - 5 V.

They are widely used in budget smart speakers, mobile phones, headsets, and other electronics. While they provide good sound quality at a low cost, they are inferior to condenser microphones in terms of sound accuracy and dynamic range.

### MEMS

MEMS (Micro-Electro-Mechanical Systems) is a microphone manufacturing technology based on microelectromechanical systems. These microphones feature miniature size, high mechanical durability, and stable performance. Their frequency range is 100 Hz – 10 kHz, sensitivity is -38 dB ±3 dB, SNR is 60-70 dB, and operating voltage is 1.6 - 3.3 V.

MEMS microphones are widely used in modern mobile devices, wireless headsets, hearing aids, and Internet of Things (IoT) devices. Their key advantages include low power consumption, resistance to electromagnetic interference, and integration with digital interfaces.

### Beamforming Array

A microphone array is a system of multiple microphones working together to improve sound capture quality and noise suppression. This technology is based on the principle of beamforming, allowing it to isolate sound from a specific direction while reducing background noise.

Key parameters depend on the array configuration and the signal processing algorithms used. MEMS microphones are most commonly used, combined into an array with digital signal processing.

Microphone arrays are widely used in smart speakers, video conferencing systems, voice assistants, and active noise cancellation systems. This enables devices to accurately recognize speech even in noisy environments and deliver high-quality sound.

# **Document Revision History**

| Version | Date | Comment | Contributor | Task |
| --- | --- | --- | --- | --- |
| v1.0 |  | Document created | @real pxkn   |  |