# Non-functional Requirements

| **NFR ID** | **Name** | Priority | **Description** | **Applies to / Covered By** | Date added | Revision History |
| --- | --- | --- | --- | --- | --- | --- |
| **NFR-001** | **Response Time** | Must-have | 1) The system should respond to basic voice commands (e.g., “What time is it?”) within **3 seconds** on average in an offline environment, ensuring minimal user frustration.

2) Time period between 2 distinct words should be no more than 0.5 seconds | Applies broadly to all user stories (US-001 to US-007), especially real-time interactions. | 13.02.2025 |  |
| **NFR-002** | **Resource Usage** | Could-have | The speaker’s STT/TTS modules must run efficiently on the Orange Pi 5. CPU usage should generally stay below 80%, and memory usage should allow core features (timers, scheduling) to remain stable without crashing. | Impacts FR-001 (STT), FR-002 (TTS), FR-003 (Offline Mode) and any story requiring real-time processing. | 13.02.2025 |  |
| **NFR-003** | **Reliability & Uptime** | Should-have | The device should function continuously for **at least 48 hours** under normal usage (roughly 50 commands/day) without manual restarts, ensuring reliable alarms/timers and event notifications. | Relevant to US-002 (timer/alarm), US-006 (event alerts). Also a general system requirement. | 13.02.2025 |  |
| **NFR-004** | **Security & Data Privacy** | Must-have | All speech data is processed **locally**. No audio or transcript leaves the local network unless explicitly enabled by an admin. Any potential cloud integration (e.g. weather) must adhere to the closed-contour policy (e.g., on-premises server, no external endpoints). | Strongly linked to FR-003 (Offline Operation) and US-007 (Use Speaker in a Closed Environment). | 13.02.2025 |  |
| **NFR-005** | **Maintainability** | Could-have | The codebase and configuration files should be modular enough to **swap** the STT/TTS engine or adapt to additional features with minimal refactoring (target: under 1 week of dev effort). | Affects FR-001, FR-002, especially if a new library or language support is needed. | 13.02.2025 |  |
| **NFR-006** | **Usability (Voice Feedback)** | Must-have | If the speaker fails to recognise a command, it politely prompts the user to **repeat** or clarifies possible commands. Error messages should remain concise and user-friendly (e.g., “I didn’t get that, please try again.”). | Primarily supports US-001 (time queries), US-002 (timers), but beneficial across all voice interactions. | 13.02.2025 |  |
| **NFR-007** | **Localisation/Accuracy** | Could-have | The system aims for at least **80% accuracy** in speech recognition for the supported languages (English/Russian) under normal acoustic conditions, ensuring basic user satisfaction. | Tied to FR-001 (STT) and any user story involving voice input. | 13.02.2025 |  |
| **NFR-008** | **Scalability** | Won’t have | The architecture should allow future deployment of **multiple speakers** in the same network, possibly sharing calendar data, events, or streaming sources, without major rework. | Applies mainly to US-004 (Scheduling), US-006 (Notifications), and any future expansions. | 13.02.2025 |  |
| NFR-009 | **Observability** | Should-have | 1. The Smart Speaker system must provide **internal visibility into its operations** to facilitate debugging, performance monitoring, and issue detection.

2. It should implement **logging, metrics, and tracing** to track **audio processing, command execution, timers, and system health**, even in an **offline environment**.

3. Logs should be **stored locally**, ensuring efficient resource usage on the OrangePi 5, with support for **error alerts and CLI-based debugging tools**. | Applies to FR-*. | 17.02.2025 |  |
| NFR-010 | **Interoperability** | Could-have | The system can communicate with external devices using standardized protocols (e.g., Bluetooth A2DP, MQTT, Wi-Fi, USB). | Tied to FR-007 and any future expansions. | 17.02.2025 |  |

# **Document Revision History**

| Version | Date | Comment | Contributor | Task |
| --- | --- | --- | --- | --- |
| v1.0 | 13.02.2025 | Document created | @Максим Кожинов   |  |