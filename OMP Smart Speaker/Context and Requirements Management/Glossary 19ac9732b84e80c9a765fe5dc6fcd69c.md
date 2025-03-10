# Glossary

### **PoC (Proof of Concept)**

A small-scale demonstration or prototype designed to **validate** the feasibility of an idea or a specific approach. In this project, the PoC verifies whether an **offline smart speaker** can realistically handle voice recognition and synthesis without continuous cloud services.

### **STT (Speech-to-Text)**

A technology that **converts spoken language** into written text. Also referred to as ASR (Automatic Speech Recognition). In this project, STT libraries (e.g., Vosk, PocketSphinx) enable the speaker to interpret user commands offline.

### **TTS (Text-to-Speech)**

A technology that **converts text** into synthesized speech. In this project, the TTS component (e.g., RHVoice, eSpeak) **generates audible responses** from the speaker without needing cloud-based services.

### **Closed Contour / Closed Network**

An environment where **no continuous internet connection** is assumed. All major data processing (STT, TTS, data retrieval) must happen **locally**, or through on-premises servers without relying on external cloud endpoints.

### **LLM (Large Language Model)**

A sophisticated **natural language processing** model that can interpret or generate text. While potentially used offline, LLMs often require **significant computational resources**, so their usage might be limited or adapted for this PoC.

### **Orange Pi 5**

A single-board **mini-computer** similar to Raspberry Pi, featuring an ARM CPU, used here as the hardware platform for the smart speaker. It has **limited CPU/RAM** relative to typical desktop environments, driving certain performance constraints.

### **R&D (Research and Development)**

An exploratory approach focused on **experimenting** with new ideas or technologies. The project’s R&D nature means requirements may evolve based on early findings and performance tests.

### **Architecture Decision Record (ADR)**

A short, structured **document** capturing an important architectural decision (e.g., choosing an offline STT library, deciding on a certain file format). Typically includes context, decision, consequences, and rationale.