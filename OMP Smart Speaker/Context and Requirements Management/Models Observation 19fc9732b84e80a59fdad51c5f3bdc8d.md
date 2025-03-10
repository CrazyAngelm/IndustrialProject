# Models Observation

## Abstract

This document outlines the evaluation of **Speech-to-Text (STT)** models for the **"Smart Speaker" project**, which aims to develop an offline, privacy-focused voice assistant for office tasks on embedded hardware (OrangePi 5 Pro). Testing was conducted on a Raspberry Pi 3 as a preliminary platform, focusing on **VOSK** and **Whisper** models. Key criteria include accuracy, latency, resource consumption, and suitability for real-time Russian-language processing. Findings indicate **VOSK** excels in low-resource scenarios, while **Whisper** offers superior transcription quality at higher computational costs. Recommendations are provided based on hardware constraints and use-case priorities.

---

## STT Model Analysis

### Tested Models

1. **VOSK**
    - **Model Versions**:
        - `vosk-model-small-ru-0.22` (45 MB)
        - `vosk-model-ru-0.42` (1.8 GB)
    - **Key Features**:
        - Real-time streaming API.
        - Low-latency responses.
        - Optimized for embedded systems.
2. **Whisper**
    - **Model Versions**:
        - `tiny` (73 MB), `base` (141 MB), `small` (461 MB), `medium` (1.42 GB)
    - **Key Features**:
        - Context-aware transcription with punctuation.
        - Higher accuracy for complex phrases.
        - Batch processing (file-based input).

---

### Comparative Evaluation

| **Criteria** | **VOSK Small** | **VOSK Large** | **Whisper Tiny** | **Whisper Base** | **Whisper Small** | **Whisper Medium** |
| --- | --- | --- | --- | --- | --- | --- |
| **Model Size** | 45 MB | 1.8 GB | 73 MB | 141 MB | 461 MB | 1.42 GB |
| **RAM Usage** | ~200 MB | ~3.5 GB | ~400 MB | ~1.3 GB | ~1.6 GB | ~3.4 GB |
| **Initialization Time** | Instant (<1 sec) | 2–3 minutes | <5 sec | <10 sec | <15 sec | ~30 sec |
| **Latency (Processing)** | 50–100 ms | 100–200 ms | 1–2 sec | 2–3 sec | 3–5 sec | 10–15 sec |
| **Accuracy (Russian)** | Good (fails on short/sharp sounds, e.g., "шла") | Excellent | Poor (misinterprets Russian as English) | Good (comparable to VOSK Small) | Excellent (context-aware) | Best (near-human) |
| **Real-Time Streaming** | ✅ Yes | ✅ Yes | ❌ No (file-based only) | ❌ No | ❌ No | ❌ No |
| **Punctuation Handling** | ❌ No | ❌ No | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes |
| **Hardware Suitability** | Raspberry Pi 3/OrangePi 5 | High-end devices only | Raspberry Pi 3 | Raspberry Pi 4+ | OrangePi 5 | Desktop/server |

---

## Key Findings

### VOSK

- **Strengths**:
    - **Real-Time Performance**: Near-instant response with streaming API.
    - **Low Resource Usage**: Ideal for embedded systems (e.g., OrangePi 5).
    - **Russian Support**: Effective for most commands, though struggles with phonetically complex words (e.g., "шла").
- **Weaknesses**:
    - Limited punctuation and contextual awareness.
    - Large model (`ru-0.42`) is resource-intensive.

### Whisper

- **Strengths**:
    - **Accuracy**: Context-aware transcription with punctuation, surpassing VOSK in complex scenarios.
    - **Scalability**: Larger models (`small`, `medium`) achieve near-human accuracy.
- **Weaknesses**:
    - **Latency**: High processing delay due to file-based input and lack of real-time streaming.
    - **Resource Demands**: Requires significant RAM and computational power.

---

## Implementation Details

### Testing Environment

- **Hardware**: Raspberry Pi 3 (4 GB RAM) as a proxy for OrangePi 5.
- **Software**:
    - **VOSK**: Integrated via Python API with real-time microphone input.
    - **Whisper**: Tested using file-based input (WAV), requiring audio conversion steps.

### Custom Scripts

- **VOSK Demo**:
    - Trigger-word detection (e.g., "Пожар" → "Иду тушить").
    - Code: [GitHub Link](https://gitlab.com) | [Start Script](https://gitlab.com).
- **Whisper Demo**:
    - Batch processing with adjustable models.
    - Code: [GitHub Link](https://gitlab.com).

---

## Recommendations

### Scenario-Based Guidance

| **Use Case** | **Recommended Model** | **Rationale** |
| --- | --- | --- |
| **Wake Word Detection** | VOSK Small | Low latency, minimal resource usage, real-time capable. |
| **Command Recognition** | VOSK Large | Higher accuracy for complex commands (if hardware permits). |
| **Transcription Tasks** | Whisper Small | Balance of accuracy and resource use; suitable for post-processing. |
| **High-Accuracy Analytics** | Whisper Medium | Deploy on servers for non-real-time tasks (e.g., meeting minutes generation). |

### Optimization Strategies

1. **Hybrid Approach**: Use **VOSK Small** for real-time wake word detection and **Whisper Small** for contextual command processing.
2. **Hardware Leverage**: OrangePi 5’s 16 GB RAM and NPU can mitigate Whisper’s resource demands.
3. **Audio Stream Handling**: Explore Whisper optimizations (e.g., chunked processing) to reduce latency.

---

## Conclusion

For the **Smart Speaker** project, **VOSK Small** is recommended for core voice interaction due to its real-time efficiency and compatibility with embedded systems. **Whisper Small** serves as a complementary tool for high-accuracy transcription where latency is tolerable. Future work should focus on integrating Whisper’s streaming capabilities and optimizing models for the OrangePi 5’s hardware.

---

# 🔔 AI-Generated Content Disclaimer 🤖

**AI Usage Self-Declaration**:

- Spelling/grammar correction: [yes]
- Technical clarity enhancement: [yes]
- Structural formatting: [yes]
- Data visualization (tables): [yes]

The author’s original experimental results and analysis form the core of this document. AI tools were used solely to enhance readability and organization.

# **Document Revision History**

| Version | Date | Comment | Contributor | Task |
| --- | --- | --- | --- | --- |
| v1.0 | 19.02.2025 | Document created | @Альберт Аксёнов   |  [Create document with models observation](https://www.notion.so/Create-document-with-models-observation-19bc9732b84e80278c29e92444fa86d6?pvs=21)  |