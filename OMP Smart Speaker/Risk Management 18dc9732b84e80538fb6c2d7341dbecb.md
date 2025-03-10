# Risk Management

# Risks table

| **Risk** | **Status** | **Probability** | **Severity** | **Description** | **Mitigation Strategy** |
| --- | --- | --- | --- | --- | --- |
| **Hardware Resource Constraints** | Active | Likely | High | Running offline STT/TTS on limited hardware (like Orange Pi/Raspberry Pi) could lead to slow performance or memory issues, causing poor user experience. | Choose efficient STT/TTS frameworks, conduct early performance tests, optimize code or offload heavy tasks (e.g., LLM) to optional external server if feasible. |
| **STT Inaccuracy** | Active | Occasional | High | Offline speech recognition might fail to recognize certain accents or paraphrased commands, harming the speaker’s usability. | Regularly evaluate STT accuracy with test phrases, adjust RHASSPY language models, gather user feedback, refine or add synonyms/intents. Implement fallback when no intent is recognized. |
| **Security & Privacy** | Active | Unlikely | High | Sensitive user data (notifications, personal logs) or partial voice data might leak if external calls are not well controlled, or if the system is exposed to network threats. | Store data locally in an encrypted database if needed, limit external connections to optional weather APIs, secure network ports, document offline usage best practices, and keep no persistent logs of raw audio. |
| **Voice Activation Issues** | Active | Occasional | Medium | The “wake word” or voice-activation phrase may trigger incorrectly or fail to trigger at all, confusing users and limiting hands-free operation. | Use tested wake-word detection from RHASSPY, conduct repeated user testing, allow manual fallback if voice activation fails. Provide a configurable sensitivity for activation phrase. |
| **Integration with External APIs** | Active | Occasional | Medium | Weather services might be unavailable, block access, or require different authentication, risking partial feature failure or unexpected delays. | Implement fallback or offline mode for weather (cached data, politely inform user if no net). |
| **Timeline Constraints** | Active | Likely | Medium | The project has multiple academic presentations; failing to demonstrate progress on each milestone could harm the final evaluation and stakeholder satisfaction. | Use short iterations with XP approach, keep an up-to-date backlog in GitLab, reevaluate scope each milestone. Prioritize essential features first (time, alarm, weather). |
| **User Identification by Voice** | Mitigated | Unlikely | Medium | Implementing per-user voice identity is technically challenging with offline approaches. Might exceed the device’s resource limits or produce false positives. | Mark as optional advanced feature. Evaluate small-scale speaker recognition module. If resource usage is too high, revert to simpler user-based PIN or skip personal notifications per voice. |
| **Team Collaboration / Customer** | Mitigated | Occasional | Medium | Inconsistent communication or shifting requirements from the customer might lead to churn and missed deliverables. | Conduct regular sync calls or chats, track changes in backlog, confirm and sign off new requirements quickly. Provide short demos to the customer after each iteration. |
| **Quality of Rhasspy Integration** | Active | Occasional | Medium | Rhasspy is open-source and may have limited community support or unanticipated bugs, leading to rework or blocked tasks. | Keep an eye on Rhasspy issues forum, do small PoCs for each new feature before major integration, maintain fallback plan with alternative STT if Rhasspy fails for a certain locale or environment. |

### Column description

**Risk**: A short name or description (e.g., “Hardware Resource Constraints”).

**Status**: Whether the risk is *Active* (still a threat), *Mitigated* (a plan is in place and working), *Occurred* (it materialised), or *Closed*.

**Probability**: The likelihood (e.g., *Likely*, *Occasional*, *Unlikely*).

**Severity / Impact**: The potential impact if it occurs (e.g., *High*, *Medium*, *Low*).

**Description**: A brief explanation of why this is a risk and how it could affect the project.

**Mitigation Strategy**: The approach or steps the team takes to reduce the probability or impact.

---

# Risks management strategy

1. **Risk identification:** brainstorm the possible risks on weekly planning calls
2. **Risk assessment:** assess the severity and probability of risks
3. **Risk mitigation:** develop strategy within the team to mitigate
risks
4. **Risk monitoring:** document identified risks and constantly review them