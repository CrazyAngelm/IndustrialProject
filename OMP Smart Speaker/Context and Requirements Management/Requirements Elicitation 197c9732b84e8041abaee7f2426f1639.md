# Requirements Elicitation

# Elicitation techniques:

## **Interviews and Brainstorming Sessions**

- **Customer Interviews**
Periodic calls or Telegram discussions with the sponsor to clarify the main use cases (voice commands, local tasks, etc.).
- **Team Brainstorming**
Internal sessions to refine feasibility (which STT/TTS libraries, how to handle offline updates, etc.).

## **Competitive / Analogous Product Analysis**

- Study existing commercial speakers (like Amazon Echo, Google Home, Yandex Station), focusing on how their offline or local modes (if any) function, gleaning insights into user expectations (voice trigger, minimal latency, etc.).
- Evaluate open-source projects that provide embedded voice processing solutions (e.g., Mycroft, Vosk, RHVoice).

## **User Story Mapping**

- Create high-level **User Stories** for each typical usage scenario: “As a user in a secure environment, I want to ask the speaker for the current time, so that I can keep track of meetings.”
- Break down stories into sub-tasks (audio capture, voice recognition, command interpretation, response synthesis, etc.).
- Prioritize them based on importance (Must/Should/Could) and feasibility.

## **Prototyping & Feedback**

- Build early prototypes of critical functions (e.g., offline STT).
- Collect immediate **feedback** from the sponsor or potential end users to see if accuracy, speed, and UI meet expectations.
- Incorporate improvements iteratively.

## **Documenting Changes**

- Store the initial set of requirements in a shared workspace.
- Log **revisions** (new user stories, scope shifts) as the project evolves (e.g., if the sponsor decides that weather integration is unnecessary or wants advanced local NLP).