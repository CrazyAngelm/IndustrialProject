# Domain-Driven Design Process

When applying **Domain-Driven Design (DDD) to a Proof of Concept (PoC)**, the goal is to **validate key business and technical assumptions** quickly while focusing on the **core domain**. Unlike a full-fledged DDD implementation, a PoC focuses on essential concepts to test feasibility without over-engineering.

# Identify the experts

## 1. Speech Recognition & NLP Expert

- Ensures accurate voice command recognition and intent detection.
- Optimizes Speech-to-Text (STT) and Natural Language Processing (NLP) models for better user interaction.
- Improves wake word detection and custom voice models to enhance offline performance.

### 2. Embedded Systems & IoT Engineer

- Ensures smooth operation on hardware, handling hardware optimization.
- Works on low-latency, real-time processing for voice commands.
- Integrates edge computing techniques to keep the system fully offline.

### 3. Python Backend & DevOps Engineer

- Manages local server deployment and optimizes APIs for communication between components.
- Implements database management (PostgreSQL) for storing user preferences and logs.
- Ensures secure, scalable, and efficient integration with smart devices.

# Common dictionary

## 1. Core Domain Terms

| Term | Definition |
| --- | --- |
| **Smart Speaker** | The hardware device responsible for processing voice commands and executing actions. |
| **Voice Command** | A spoken input provided by a user to control the smart speaker. |
| **Wake Word** | A specific word or phrase that activates the smart speaker (e.g., "Hey Speaker"). |
| **Natural Language Processing (NLP)** | The field of AI that enables the smart speaker to understand and interpret human language. |
| **Speech-to-Text (STT)** | A process that converts spoken words into textual data for further processing. |
| **Text-to-Speech (TTS)** | A process that converts textual data into spoken output. |
| **Command Processing** | The logic that determines the intent behind a user’s voice command and executes the appropriate action. |
| **Skill** | A specific functionality that the smart speaker can perform (e.g., scheduling a meeting, setting a reminder). |
| **Intent Recognition** | The process of determining the user's intention from a voice command (e.g., "What time is it?" → Intent: GetCurrentTime). |
| **Context Awareness** | The ability of the smart speaker to understand user interactions within a conversation context. |
| **Custom Wake-Up Logic** | A system to filter out background noise and activate the device only when the wake word is detected. |

## 2. Meeting & Office Integration Terms

| Term | Definition |
| --- | --- |
| **Meeting Scheduling** | The process of booking a meeting room and notifying participants. |
| **Meeting Room Identification** | The ability to recognize and identify which room the smart speaker is operating in. |
| **Room Status** | The availability of a meeting room (e.g., occupied, available). |
| **Calendar Integration** | The connection between the smart speaker and office scheduling systems (e.g., Google Calendar, Microsoft Outlook or custom one). |
| **Voice Memo Recording** | The ability to record audio for later transcription or note-taking. |
| **Audio Streaming** | The process of sending audio (e.g., MP3) from external device |
| **Document Projection** | The process of sending a file (e.g., PDF) from a phone or computer to a screen in the meeting room. |
| **Office Automation** | The use of the smart speaker to control office devices (e.g., lights, projectors, air conditioning). |

## 3. System Architecture & Development Terms

| Term | Definition |
| --- | --- |
| **Finite State Machine (FSM)** | A model used to manage sequential interactions, such as multistep voice commands. |
| **Bounded Context** | A logical boundary within the system where specific domain concepts are defined consistently. |
| **Aggregate** | A cluster of domain objects that are treated as a single unit. |
| **Aggregate Root** | The main entity in an aggregate that controls interactions with related objects. |
| **Domain Service** | A service that contains business logic that doesn't naturally fit inside an entity or value object. |
| **Repository** | A design pattern that abstracts data storage and retrieval logic. |
| **Event-Driven Architecture** | A software architecture where system components communicate by generating and responding to events. |
| **Message Broker** | A middleware system that enables communication between different components (e.g., RabbitMQ, Kafka). |
| **Edge Computing** | Processing data locally on the smart speaker instead of sending it to the cloud. |
| **Offline Mode** | The ability of the smart speaker to function without an internet connection. |
| **Local Processing** | The ability to process voice commands without sending data to external servers, improving privacy. |

## 4. Hardware & Deployment Terms

| Term | Definition |
| --- | --- |
| **OrangePi 5** | The hardware platform used for the smart speaker. |
| **Microphone Array** | A set of multiple microphones used to capture voice input from different directions. |
| **Speaker Output** | The built-in speaker used for responding to voice commands. |
| **Docker Container** | A lightweight, portable environment for running software on the smart speaker. |
| **PostgreSQL** | The database used for storing processed commands, meeting schedules, and logs. |
| **FastAPI** | The backend framework used for handling smart speaker API requests. |
| **MQTT Protocol** | A lightweight messaging protocol for device-to-device communication. |
| **WebSocket Communication** | A real-time communication protocol for interacting with the smart speaker. |
| **Closed Contour / Closed Network** | An environment where no continuous internet connection is assumed. All major data processing (STT, TTS, data retrieval) must happen locally, or through on-premises servers without relying on external cloud endpoints. |
| **Local server** | A self-hosted server running on a local network or device, enabling offline processing and reducing dependency on external cloud services. |

## 5. Rhasspy Domain Terms

| **Term** | **Definition** |
| --- | --- |
| **Rhasspy** | An open-source, fully offline set of voice assistant services supporting multiple languages. It integrates with home automation systems and allows customization of voice commands. |
| **Voice Command Template** | A structured format used in Rhasspy to define expected voice commands. Templates specify patterns and slots to capture user intents and entities. |
| **Slots** | Placeholders within voice command templates that capture variable information from user input. For example, in the command "turn on the [device]", "device" is a slot that can hold values like "light" or "fan". |
| **Training** | The process of compiling voice command templates and slot values into a language model that Rhasspy uses to recognize speech and intents. |
| **Intent** | A high-level representation of a user's request or command. It encapsulates the meaning of an utterance and is mapped to specific actions or responses. Example: "Turn on the lights" → Intent: `TurnOnDevice`. |
| **Intent Recognition** | The process of identifying the user's intention from their spoken input. Rhasspy maps voice commands to predefined intents, enabling appropriate actions in connected systems. |
| **Intent Handling** | The mechanism that defines actions to be taken when a specific intent is recognized. Rhasspy can be configured to execute commands or send messages to external systems based on identified intents. |
| **Event** | A system-generated occurrence triggered by user interaction or an external condition. Events can be used to notify other components of actions, such as "Wake Word Detected" or "Intent Recognized". |
| **Profiles** | Configurations that define language-specific settings and resources in Rhasspy. Profiles determine how Rhasspy processes speech for a particular language or dialect. |
| **Voice Model** | A machine learning model used to recognize spoken words and phrases. It is trained on speech data and helps convert audio input into text for further processing. |
| **Wake Word** | A specific word or phrase that activates the voice assistant, prompting it to listen for commands. Rhasspy supports customizable wake words to initiate interaction. |
| **Speech-to-Text (STT)** | The component that converts spoken language into written text. Rhasspy utilizes various STT engines to transcribe user speech into text for further processing. |
| **Text-to-Speech (TTS)** | The component that converts text responses into spoken language. Rhasspy employs different TTS engines to vocalize responses back to the user. |
| **MQTT (Message Queuing Telemetry Transport)** | A lightweight messaging protocol used by Rhasspy to communicate with other services and home automation platforms. |

# Event Storming

Event Storming Board: [Viewer Link](https://miro.com/app/board/uXjVIa79Rfc=/?share_link_id=460369918022)

# **Document Revision History**

| Version | Date | Comment | Contributor | Task |
| --- | --- | --- | --- | --- |
| v1.0 | 24.02.2025 | Document created | @Самат Гатин  | [issue-#29](https://gitlab.pg.innopolis.university/smart-speaker-group/smart-speaker-codebase/-/issues/29) |