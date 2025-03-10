# Attribute-Driven Design Process

The ADD method is an approach to defining a software architecture in which the design process is based on the quality attribute requirements the software must fulfill. ADD follows a recursive process that decomposes a system or system element by applying architectural tactics and patterns that satisfy its driving quality attribute requirements.

Steps of ADD:

1. Review inputs
    1. Clarify what we are solving:
        1. Business goals
        2. Functional requirements
        3. Quality requirements (non-functional)
        4. Constraints (business, environment, existing systems)
2. Establish iteration goal
    1. What design issue are we trying to solve in the iteration?
3. Identify elements of the system to refine
    1. **For iteration 0, you decompose the entire system.**
    2. For any other iteration, you pick one or more of the existing elements from previous iterations.
4. Choose design concepts that satisfy inputs
    1. Identify concerns associated with selected architectural drivers. Example: Introducing change is expensive (if every component is connected to every other component).
    2. List potential patterns and tactics that you can apply to address the concerns.
    3. Make a trade-off analysis.
    4. Check how patterns coexist and integrate.
    5. Plan for how you would verify that the selected design achieves the goal.
5. Allocate responsibilities and define interfaces
    1. Instantiate elements.
    2. Describe responsibilities of the elements.
    3. Define public interfaces of the elements.
6. Sketch views and record design decisions
    1. Write down all info about components that you discovered in previous steps.
    2. Describe the solution using diagrams.
    3. Write down all the design decisions.
    4. Describe the alternatives and why they were not selected.
7. Perform analysis and review the iteration goal
    1. Review all the artifacts that you created and make sure the iteration fulfills the goals.
        1. Write down how you know what you proposed actually achieves the goal.
        2. Ask someone else to review your conclusion.

# System Description

[*Context and Requirements Management*](../Context%20and%20Requirements%20Management%2018dc9732b84e80a6abe9eefc4a38617d.md)

# Core Components and Tecnical Stack

- **Hardware**: **OrangePi 5**
- **Operating System**: Linux-based (Armbian or Debian)
- **Programming Language**: **Python**
- **STT (Speech-to-Text)**
- **TTS (Text-to-Speech)**
- **Database**: **SQLite** (lightweight) or **PostgreSQL** (if persistence is critical)
- **Event Scheduler:** Custom web-interface
- **Notification System**: Local message queue
- **Audio Streaming Module**: Audio stream from phone (Bluetooth)

# Itreration 0 diagrams

The initial architecture according core components.

| **Element** | **Description** | **Role in the System** |
| --- | --- | --- |
| **User** | The person interacting with the smart speaker through voice or text input. | Initiates requests, issues commands, and receives responses. |
| **Microphone / Keyboard** | Captures **audio input** (speech) or **text input** (manual entry). | Provides raw input for processing. |
| **Speech-to-Text (STT)** | Converts spoken language into text using an offline STT engine (e.g., **Vosk, Whisper**). | Enables **voice command processing** by converting speech into machine-readable text. |
| **NLU/Parser (Natural Language Understanding)** | Analyzes the transcribed text to extract **intent and entities** (e.g., time, actions). Uses **machine learning or rule-based models**. | Detects the **user's intent** and determines the required action. |
| **Detected Intent** | The extracted intent (e.g., "Set an alarm for 7 AM"). This includes structured data like **command type, parameters, and entities**. | Passes the **recognized command** to the execution layer for further processing. |
| **Code/Skill Module** | A collection of skills or functions that execute the requested task (e.g., managing timers, fetching weather, retrieving calendar events). | Performs actions based on the **recognized intent**, such as setting alarms or retrieving data. |
| **Database** | Stores local data, including **alarms, calendar events, notifications, and cached weather information**. | Provides persistent storage for **offline operation** and quick data retrieval. |
| **Text-to-Speech (TTS)** | Converts generated responses from text into **natural-sounding speech** (e.g., **Piper, VITS, eSpeak**). | Enables **spoken responses**, making interactions **hands-free**. |
| **Speaker Output** | Plays back the synthesized speech to the user. | Delivers **audible responses** to user queries. |

![v0.1](Attribute-Driven%20Design%20Process%2019ac9732b84e8043b55fdd9a2bbbce9b/General_architecture_of_a_voice_assistant.drawio.png)

v0.1

Clarification after realising that detected intent is not a separate component of a system. Combined NLU and Intent detection to a single module named Dialog Module.

![v0.2](Attribute-Driven%20Design%20Process%2019ac9732b84e8043b55fdd9a2bbbce9b/General_architecture_of_a_voice_assistant_v2.drawio.png)

v0.2

According to Functional Requirements we added specified componets as Internal APIs (not all of them shown on the diagram):

- Timer
- Scheduler
- Audio Streaming Module
- Notification System

Added placeholders for System Configuration Management, External APIs and External Server.  

![v0.3 - The final diagram of iteration 0](Attribute-Driven%20Design%20Process%2019ac9732b84e8043b55fdd9a2bbbce9b/General_architecture_of_a_voice_assistant_v3.jpg)

v0.3 - The final diagram of iteration 0

# Events Flowing Through the Smart Speaker System

Based on the Must-have functional requirements, here is a structured list of **all events** that go through the system:

| **Event Category** | **Event Name** | **Description** |
| --- | --- | --- |
| **User Interaction Events** | User speaks a command | Captures audio from the microphone and processes it. |
|  | User manually inputs text (if supported) | Allows text-based input instead of voice. |
|  | User cancels an active command | Stops ongoing processing. |
| **Speech Processing Events** | Audio signal received | Captured audio is sent to **Speech-to-Text (STT)**. |
|  | Speech-to-Text processing starts | Converts speech into text. |
|  | Text successfully converted | Sent to **Natural Language Understanding (NLU)**. |
|  | Detected text is invalid or unclear | System requests a repeat or handles errors. |
|  | Intent detected and processed | System determines the user's intent. |
|  | Response generated | System prepares a response. |
|  | Text-to-Speech (TTS) conversion | Converts text into speech. |
|  | Audio playback starts | Speaker outputs the generated response. |
| **Command Processing Events** | Command identified | Matches user input with known actions. |
|  | Command requires data retrieval | Fetches data from local storage. |
|  | Command requires an action | Executes tasks (e.g., setting timers, alarms). |
|  | Command execution succeeds | Confirms via TTS. |
|  | Command execution fails | Notifies the user of failure. |
| **Timer & Alarm Events** | Timer is set | Stores and schedules the timer. |
|  | Timer reaches zero | Triggers an alert. |
|  | Alarm is scheduled | Records alarm time. |
|  | Alarm goes off | Plays an alert or TTS announcement. |
|  | User stops or snoozes alarm | Updates alarm state. |
| **Calendar & Notification Events** | User creates a calendar event | Stores event in **local database**. |
|  | User queries upcoming events | Fetches and announces scheduled events. |
|  | Notification is scheduled | Prepares for future alerts. |
|  | Notification is triggered | Plays an alert or TTS message. |
|  | User acknowledges or dismisses notification | Updates system state. |
| **Configuration & System Events** | User modifies settings via web interface | Updates configuration. |
|  | System starts up | Loads configurations and initializes components. |
|  | System shuts down | Saves state and safely exits. |
|  | System encounters an error | Logs issue and optionally notifies the user. |

# Practical Example of Applying Attribute-Driven Design

## Introduction

The Scheduler module is a crucial component of the **Smart Speaker** system, responsible for handling time-based tasks, such as alarms and notifications. This module must operate within the constraints of an embedded system (OrangePi 5) while ensuring efficient and reliable task execution. This section describes how the **Attribute-Driven Design (ADD) process** was applied to refine the Scheduler module over multiple iterations.

---

## Iteration 0: Baseline Architecture

The initial system architecture included the following core components:

- **Speech-to-Text (STT)**: Converts spoken commands into text.
- **Dialog/Intent Module**: Interprets user commands.
- **Code/Skill Module**: Handles task execution.
- **Database**: Stores persistent data.
- **Text-to-Speech (TTS)**: Converts text responses into spoken output.
- **Internal APIs**: Includes modules like Scheduler and Timer.

At this stage, the **Scheduler** existed as a basic component without detailed mechanisms for managing scheduled tasks.

---

## Iteration 1: Implementing a Core Scheduling Mechanism

### **Step 1: Review Inputs**

The primary requirements identified were:

- **FR-005**: The system must support alarms and notifications.
- **Performance constraint**: The scheduling mechanism should have low CPU and memory overhead.

### **Step 2: Establish the Iteration Goal**

The objective was to implement a **lightweight scheduling mechanism** capable of handling **one-time tasks** (alarms, reminders) efficiently.

### **Step 3: Identify Elements to Refine**

This iteration focused on refining the **Scheduler** and its interactions with the **Timer** module.

### **Step 4: Choose Design Concepts**

Several design patterns were considered:

- **Observer Pattern**: Provides flexibility for event-driven notifications but introduces additional complexity.
- **Timer Queue Pattern** (*Selected*): Offers a straightforward approach for handling time-based events with minimal overhead.

### **Step 5: Allocate Responsibilities and Define Interfaces**

The **Scheduler** was designed to manage a queue of time-based events. The following responsibilities were defined:

- **Queue Management**: Maintain a queue of scheduled tasks.
- **Task Execution**: Trigger events when their scheduled time arrives.
- **Notification Handling**: Inform the system when tasks are executed.

**Key API Methods:**

- `add_task(time, action)`: Schedule a one-time task.
- `remove_task(task_id)`: Cancel a scheduled task.
- `execute_task(task_id)`: Execute a scheduled task.

### **Step 6: Sketch Views and Record Decisions**

The Scheduler was connected to a **TimerQueue**, which tracked and executed scheduled tasks. The **Observer Pattern** was not used in this iteration to keep the design simple.

![2.PNG](Attribute-Driven%20Design%20Process%2019ac9732b84e8043b55fdd9a2bbbce9b/2.png)

### **Step 7: Perform Analysis**

Tests confirmed:

- **Reliable task execution** for alarms.
- **Minimal resource usage**, ensuring suitability for an embedded environment.
- The system met the **functional requirements (FR-005)** while maintaining efficiency.

---

## Iteration 2: Adding Support for Recurring Tasks

### **Step 1: Review Inputs**

- **FR-009**: The system must support **recurring tasks** (daily alarms, weekly reminders).
- **Modifiability**: New task types should be easy to implement.

### **Step 2: Establish the Iteration Goal**

The objective was to extend the Scheduler to handle **recurring events** while maintaining low overhead.

### **Step 3: Identify Elements to Refine**

- The **Timer Queue** was insufficient for recurring tasks, requiring a more flexible mechanism.

### **Step 4: Choose Design Concepts**

Two approaches were considered:

- **Cron-style Scheduling**: Uses OS-level features but adds external dependencies.
- **State-Based Scheduling** (*Selected*): Implements task recurrence within the Scheduler’s logic without relying on OS mechanisms.

### **Step 5: Allocate Responsibilities and Define Interfaces**

Enhancements to the Scheduler included:

- **State-Based Task Management**: Tasks transition between `waiting`, `executing`, and `rescheduling` states.
- **New API Methods**:
    - `add_recurring_task(interval, action)`: Schedule a recurring task.
    - `remove_recurring_task(task_id)`: Cancel a recurring task.
    - `execute_recurring_task(task_id)`: Execute a recurring task and reschedule.

### **Step 6: Sketch Views and Record Decisions**

The updated Scheduler **tracks recurring tasks** and transitions them through different states, ensuring they execute at specified intervals.

![3.PNG](Attribute-Driven%20Design%20Process%2019ac9732b84e8043b55fdd9a2bbbce9b/3.png)

### **Step 7: Perform Analysis**

Tests showed that the new mechanism:

- **Successfully handled recurring events**, such as daily alarms.
- **Simplified modification**, allowing easy extension for future scheduling features.

---

## Conclusion and Discussion

Between Iteration 1 and Iteration 2, I moved from a simple Timer Queue for single events to
a more flexible, state-based system for recurring tasks. The main trade-offs I considered
involved complexity and resource usage. In the end, the Scheduler design feels balanced for
our low-powered device, and I can see how it might be expanded for future needs (like more
sophisticated scheduling or additional event types).

## Final Artifacts

1. Iteration 0 Diagram: Basic architecture of the entire system.
2. Iteration 1 Diagram: Shows how the Scheduler interacts with the Timer Queue for
single tasks.
3. Iteration 2 Diagram: Shows a state-based approach for recurring tasks.

# Smart Speaker based on Rhasspy framework

![General architecture of a voice assistant v4 modularity.drawio.png](Attribute-Driven%20Design%20Process%2019ac9732b84e8043b55fdd9a2bbbce9b/General_architecture_of_a_voice_assistant_v4_modularity.drawio.png)

# **Document Revision History**

| Version | Date | Comment | Contributor | Task |
| --- | --- | --- | --- | --- |
| v1.0 | 17.02.2025 | Document created | @Самат Гатин  |  |
| v1.1 | 19.02.2025 | [Added Scheduler architecture](Attribute-Driven%20Design%20Process%2019ac9732b84e8043b55fdd9a2bbbce9b.md) | @Альберт Аксёнов  |  |