# User Stories & Functional Requirements

# **User Stories**

| **ID** | **Title** | **Description** | **Priority** | **Acceptance Criteria** | Status | **Covered FRs** | Date added | Revision History |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| US-001 | Ask for Current Time | As a user,
I want to ask the speaker for the current time, 
so that I can quickly get the information without checking a clock. | Must-have | 1. When the user says keywords like “What time is it?” or “Give me the current time,” the system responds with the correct local time within X seconds.

2. The time announced is accurate to the system clock.

3. The speaker operates offline for this feature (no internet required). | in-progress | FR-001, FR-002, FR-003 | 10.02.2025 |  |
| US-002 | Set a Timer/Alarm | As a user,
I want to set a timer (or alarm) on the speaker,
so that I can be reminded after a specific duration. | Must-have | 1. User can say “Set a timer for 5 minutes” or “Wake me up at 7 AM.”

2. Speaker confirms verbally that the timer/alarm has been set.

3. After the duration or at the specified time, the speaker plays a sound or TTS notification.

4. It must work without internet access. | not started | FR-001, FR-002, FR-004 | 10.02.2025 |  |
| US-003 | Local Weather Information | As a user,
I want to ask about the local weather,
so that I can pick proper clothes when going outside. | Should-have | 1. User can say “What’s the weather like today?”|

2. If a local weather service is configured, the system retrieves basic weather info (temperature, precipitation) from a local server (or cached data).

3. If no network is available, the system politely states it is unable to retrieve weather data. | not started | FR-001, FR-002, FR-003, FR-005 | 10.02.2025 |  |
| US-004 | Schedule/Calendar Management | As a user,
I want to add and hear upcoming events,
so I can manage my daily schedule hands-free. | Must-have | 1. User can say “Add a meeting on Friday at 10 AM” or “What’s on my schedule for today?”

2. If using local calendar storage, the speaker must update or retrieve events offline.3. The speaker provides simple responses: “You have a meeting at 10 AM,” or “No events found.” | not started | FR-001, FR-002, FR-006 | 10.02.2025 | Updated to must |
| US-005 | Streaming Audio from Mobile Device | As a user,
I want to stream music or audio from my phone to the speaker, so I can use the speaker’s sound system. | Could-have | 1. The speaker can receive an audio stream (Bluetooth or local Wi-Fi).

2. The user triggers playback on the mobile device, and the speaker outputs the sound.

3. The system requires minimal configuration steps (pairing or local network detection).

4. No direct internet streaming is mandatory. | not started | FR-007 | 10.02.2025 |  |
| US-006 | Voice Notification for Events | As a user,
I want the speaker to notify me verbally of upcoming tasks or emergency alerts,
so I don’t miss important updates. | Should-have | 1. The speaker can store or receive notifications from a local server (like an event or emergency system).

2. When an alert triggers, the speaker announces it verbally (e.g. “Meeting in 10 minutes”).

3. Must work in offline or partially connected scenarios. | not started | FR-001, FR-002, FR-008 | 10.02.2025 | Milestone 1 - revision |
| US-007 | Use Speaker in a Closed Environment | As a user,
I want to ensure all speech data stays inside the local network, 
so that sensitive info is not sent to external servers. | Must-have | 1. The system processes TTS and STT locally (no external cloud calls).

2. Any partial updates or weather data are retrieved from an on-premises server if needed.

3. Admin can configure network settings to ensure no external endpoints are used. | not started | FR-001, FR-003, FR-005 | 10.02.2025 |  |
| US-008 | Configure system from Web-interface | As a developer,
I want to change system’s configuration rapidly,
so I can test and fix system faster. | Should-have | 1.  To change the system configuration, at least a reboot will be required.

2. System correctly changes behavior accordingly to new configuration. | not started | FR-009 | 17.02.2025 |  |
| US-009 | Transmit audio responses | As a user,
I want to hear audio message from Smart Speaker,
so I can receive responses to my requests in audible way. | Must-have | 1.  All information to user interactions will come from system dynamics.

2. System is capable of translating all responses into audio format.

3. Audio messages are audible and understandable to user. | not started | FR-009 | 17.02.2025 |  |
| US-010 | Voice Command Recognition | As a user,
I want the speaker to recognize my voice commands, 
so that I can control it hands-free. | Must-have | 1. The system recognizes basic control commands like “Turn on”, “Turn off”, “Increase volume”, etc.

2. Commands are processed locally without requiring an internet connection.

3. The system provides feedback if a command is not understood. | not started | FR-001, FR-003 | 20.02.2025 | Added after meeting with customer - 17.02 |
| US-011 | System Control via Voice (Sound) | As a user, 
I want to control the speaker system via voice, 
so that I can adjust settings like volume or mute without using buttons. | Must-have | 1. User can say commands like “Increase volume”, “Mute speaker”, “Set volume to 50%”.

2. The system confirms the command with an audio response.

3. Settings are adjusted in real-time. | not started | FR-001, FR-003 | 20.02.2025 | Added after meeting with customer - 17.02 |
| US-012 | User Recognition via Voice | As a user,
I want the speaker to recognize my voice and distinguish it from others,
so that my personal settings and reminders remain private. | Could-have | 1. The system identifies users based on voice patterns.

2. Only authorized users can access personal reminders, schedules, and preferences.

3. If an unrecognized voice gives a command, the system requests authentication or denies access. | not started | FR-001, FR-009, FR-010 | 20.02.2025 | Added after meeting with customer - 17.02 |
| US-013 | Wake-up on Voice Command | As a user,
I want the speaker to wake up and start listening when I say a specific activation phrase,
so that I don’t need to press a button. | Should-have | 1. The speaker listens for a wake word (e.g., “Hello Speaker”) and activates automatically.

2. The activation process happens locally with minimal delay.

3. The system ensures false activations are minimized. | not started | FR-001, FR-003, FR-011 | 20.02.2025 | Added after meeting with customer - 17.02 |
| US-014 | LLM request recognition | As a user,
I want the speaker to understand different forms of same commands,
so that there will be unlimited amount of way to trigger event | Must-have | 1. Speaker can consume and classify different types of commands

2. Speaker can classify unusual variations of commands into system events | not started | FR-001 | 06.03.2025 | Added after meeting with customer - 3.03 |

<aside>
💡

MoSCoW prioritisation technique used:

- “Must-have” means essential for the core PoC.
- “Should-have” are important but can be postponed if time is limited.
- “Could-have” is nice to explore if resources allow.
- “Won’t-have” will not be implemented in this project
</aside>

# **Functional Requirements**

Table linking each **Functional Requirement (FR)** to the relevant User Stories.

| **FR ID** | **Name** | **Description** | **Covered By (User Stories)** |
| --- | --- | --- | --- |
| FR-001 | Local Speech Recognition (STT) | The system must capture audio from the device’s microphone and process speech recognition locally (e.g., using an offline STT engine). It should handle basic commands like “What time is it?” or “Set timer for 10 minutes” in the primary language (e.g., English/Russian). | US-001, US-002, US-003, US-004, US-006, US-007 |
| FR-002 | Speech Synthesis (TTS) | The system must generate spoken replies locally, with minimal latency, using an offline TTS engine. It should handle short responses (< 30 words) for confirmations, time announcements, or schedule readouts. | US-001, US-002, US-003, US-004, US-006, US-009 |
| FR-003 | Offline/Closed-Contour Operation | The speaker must run core functionalities (command recognition, basic data retrieval) without requiring internet access. If partial connectivity exists, ensure no critical tasks break when offline. | US-001, US-003, US-007 |
| FR-004 | Timer/Alarm Management | The speaker must store and track multiple timers/alarms. When time is up, it should trigger an audible alert or TTS. The system must handle basic time-based commands (e.g., “Set an alarm at 7 AM,” “Cancel alarm,” etc.). | US-002 |
| FR-005 | Local/On-Prem Weather Fetch | If a local weather service is configured, the system can fetch weather data from it. If unavailable, the system politely notifies the user. The speaker should never call external APIs directly. | US-003, US-007 |
| FR-006 | Calendar/Schedule Storage | The system must support basic calendar operations in offline mode. For instance, store events in a local database or retrieve events from an internal server. The user can query upcoming events and receive spoken feedback. | US-004 |
| FR-007 | Audio Streaming Input | The speaker can accept audio streams from a paired device (e.g., via Bluetooth A2DP or local Wi-Fi). This is optional for the PoC but should be supported if time permits. | US-005 |
| FR-008 | Notification/Alert Delivery | The speaker can receive or store notifications (scheduled or event-based) and deliver them by voice at the appropriate time. This includes emergency alerts or upcoming tasks. | US-006 |
| FR-009 | Configuration management | The system must be configurable to throw the web-interface. | US-008 |
| FR-010 | Voice-Based User Identification | The system should recognize individual users based on voice and restrict access to personal data accordingly. | US-012 |
| FR-011 | Wake Word Detection | The system should listen for a predefined wake word and activate without requiring physical interaction. | US-013 |
| FR-012 | LLM speach recognition | The system should consume different forms of commands and classify it into programmed events. | US-014 |

# **Document Revision History**

| Version | Date | Comment | Contributor | Task |
| --- | --- | --- | --- | --- |
| v1.0 | 10.02.2025 | Document created | @Максим Кожинов
@Самат Гатин  |  |
| v1.1 | 21.02.2025 | Document updated after customer validation | @Максим Кожинов  |  |