# Project Planning

# Strategic planning

[Project timeline](Project%20Planning%2018dc9732b84e80a09abdd57385482b36/Project%20timeline%2018dc9732b84e80c497dbe4ea66d806d8.csv)

## Milestone 1

**Dates:** 27.01 - 17.03

**Sprints:** 1 - 5

**Goals:** 

1. Collect and document all **functional and non-functional requirements** (user stories, initial constraints) and confirm the scope with the customer.
2. Establish and document **project planning**, **project tracking**, **risk management**, **configuration management**, **quality management**, **context/requirements management**, and **architectural design** pages required by the university & create presentation
3. Set up the **RHASSPY** framework for a minimal command (e.g., “What time is it?”) and demonstrate basic STT/TTS offline.
4. Prepare an **initial architectural diagrams** for the smart speaker.
5. Validate the overall plan, **technology stack**, and libraries with the customer and mentor.

**DoD:**

1. Requirements are documented (functional, non-functional) with initial user stories.
2. All seven practice-area pages have **basic** content (draft form).
3. RHASSPY can process a single voice command (“What time is it?”) and respond with TTS.
4. Basic risks are identified and stored in a risk register.
5. The mentor and customer approve the plan and the minimal speaker demo.

## Milestone 2

**Dates:** 18.03 - 14.04

**Sprints: 6** - 9

**Goals:** 

1. Extend the **RHASSPY** configuration to handle multiple basic commands (e.g., “Set alarm,” “Tell me notifications,” “Activate speaker by voice trigger”).
2. Implement a local **database** (e.g., SQLite) to store alarms, notifications, or user data offline.
3. Update Architectural ****diagrams to show how each module interacts (alarm handling, data storage).
4. Refine **risk management** by adding new risks discovered during development.
5. Improve documentation in **architectural design**, **quality management**, and **configuration management** based on feedback from Milestone 1.
6. Evaluate potential **LLM integration** for paraphrased/unusual user queries, if feasible.

**DoD:**

1. The speaker can set simple alarms (“Set alarm at 7 AM”) and store them locally.
2. A voice trigger phrase (e.g., “Hey Speaker”) is configured for basic activation.
3. The local DB is operational for storing alarms/notifications.
4. Architectural diagrams now reflect sub-components (Level 3) for alarm/notification logic.
5. Updated practice-area pages with more detail (risk register expanded, improved architecture docs).

## Milestone 3

**Dates:** 15.04 - 19.05

**Sprints:** 10 - 14

**Goals:** 

1. Integrate **weather** queries using partial internet access or a local weather API (via RHASSPY intent).
2. Enhance **RHASSPY** for more complex command phrasing (e.g., synonyms, paraphrased requests).
3. Conduct deeper **quality management** checks, including performance tests for STT/TTS.
4. Add more detailed **architecture** visualizations for any critical modules (alarm, weather).

**DoD:**

1. The speaker can handle “What’s the weather?” (pulling data from an API if available).
2. RHASSPY can handle 2–3 variations of each command (“Set alarm,” “Schedule alarm,” etc.).
3. C4 Level 4 diagrams created for at least one key component (e.g., weather retrieval or alarm scheduling).
4. Updated performance/quality checks prove the system can respond within an acceptable time.
5. The second presentation demonstrates alarms plus weather functionality.

## Milestone 4

**Dates:** 20.05 - 23.06

**Sprints:** 15 - 19

**Goals:** 

1. Add a minimal **UI** (web or mobile) for managing alarms, notifications, or weather settings if time allows.
2. Explore **voice identification** (optional advanced feature) to differentiate users.
3. Strengthen **architecture** with a final pass of documentation using C4 and config management details.
4. Refine **risk management** for new complexities (user identification, UI security).

**DoD:**

1. A simple UI is accessible to set/view alarms or weather preferences.
2. Basic user-based separation if voice identification is partially implemented (optional advanced feature).
3. Architecture docs fully detail how the UI interacts with the speaker and how user identity is handled if voice identification is used.
4. Third presentation highlights the UI usage or the advanced voice identification feature.

## Milestone 5

**Dates:** 24.06 - 28.07

**Sprints:** 20 - 24

**Goals:** 

1. Final **polishing** of all smart speaker features (voice activation, alarms, notifications, weather).
2. Hardening for a **closed environment** deployment (ensure minimal external dependencies, confirm data privacy).
3. Complete all **practice areas** with final documentation and acceptance tests (context/requirements, planning, tracking, risk, quality, architecture, config) & create comprehensive presentation 
4. Validate performance and reliability in continuous usage.
5. Provide a final **PoC demo** and user guide to the customer and mentor.

**DoD:**

1. The speaker reliably responds to all core commands offline, weather included (if net is available).
2. Data privacy is confirmed; no external calls except optional weather or LLM if enabled.
3. All seven practice-area docs are finalized (including updated risk register, final architecture diagrams, and quality metrics).
4. The final demonstration shows a stable, easily configurable speaker with voice activation.
5. The mentor and customer sign off on the PoC as meeting the major requirements.

---

# Tactical Planning

Our team follows an **eXtreme Programming (XP)**–inspired approach with **weekly** iterations rather than strict Scrum sprints. We still use some sprint-like concepts for clarity (e.g., each iteration is labeled as “Sprint #” in GitLab), but we prioritize continuous collaboration, frequent feedback, and flexible scheduling. Below is an overview:

## **Weekly Iterations and Calls**

### **Saturday Call**

- Re-evaluate all tasks, refine the backlog, and re-prioritize if needed
- Discuss any blockers or risks
- Assign tasks based on each person’s weekly capacity (about 12 hours)
- Conduct a brief retrospective (what worked well, what didn’t)
- Plan the next iteration’s goals and tasks

### **Wednesday Mid-Iteration Call**

A shorter sync to check statuses, see if anyone is stuck, and handle urgent issues before the weekend.

### **Monday Customer Call**

We demo or briefly show progress to our customer, gather feedback, and adjust tasks if requirements changed.

### **Friday Mentor Call**

We present the current work to our mentor, discuss any university-related requirements, and refine our approach.

### Telegram Chats

There are 3 chats in telegram we actively use to collaborate within a team and talk to customer & mentor.

## **Backlog & Task Management in GitLab**

All tasks (user stories, technical tasks, documentation needs) are managed as **issues** in GitLab.

We use **four labels** on each issue:

- **Sprint** (e.g., Sprint 5) to group tasks in the current iteration.
- **Source** (e.g., Customer, Mentor, University, Tech Requirement) to show where the task originated.
- **Priority** (High, Medium, Low) to ensure we tackle the most critical items first.
- **Paired Person** (the second individual who will review or assist with the task).

Our GitLab board columns typically include:

- **Not Started** (selected backlog items for the current sprint)
- **In Progress** (actively worked on)
- **Review** (waiting for peer review)
- **Done** (meets the Definition of Done for that iteration)

## **Pairing & Review Process**

- While true pair programming is challenging due to scheduling constraints, we approximate it by assigning each issue to one developer and designating a second “paired” reviewer via the **Paired Person** label.
- Once the primary developer finishes, the task moves to **Review**. The reviewer checks the code, tests the feature, and may coordinate with the developer to fix or refine any issues.
- This practice ensures **knowledge sharing** and code quality similar to XP’s pair programming principle, even if it’s not literal side-by-side programming.

## **Continuous Collaboration**

- We communicate daily through a shared **Telegram** channel to quickly resolve small blockers or questions.
- Because the customer is highly responsive in the chat, we can adapt the backlog on short notice if priorities change or new insights emerge.

## **Relation to Milestones**

- We have **five strategic milestones** (aligned with major presentations and PoC objectives).
- Each milestone spans several weekly iterations (what we colloquially call “sprints”). Milestone goals guide our backlog priorities.
- At the end of each milestone, we deliver a significant increment of functionality (e.g., offline TTS/STT, wake word activation, weather integration, etc.).

---

## **Estimation Techniques**

### **Task-Based Hour Estimation**

- We discuss each task in our Saturday call and assign a rough **hour estimate** (e.g., 2h, 4h, 6h) based on complexity.
- We don’t do formal “Planning Poker”; we rely on conversation and the team’s collective experience.

### **Weekly Capacity**

- Each developer is assumed to have about **12 hours** per week.
- We distribute tasks accordingly, ensuring no one is overloaded.

### **Refining & Re-estimating**

- If a task grows in complexity mid-week or after the mid-iteration call, we re-estimate or split the task.
- We adjust the backlog if new high-priority items arrive.

### **Retrospective on Estimates**

- During the Saturday retrospective, we quickly review where estimates differed from actual time.
- This helps us gradually improve our estimation accuracy.

---

## **Why This XP-Like Approach?**

- **Frequent Feedback**: The weekly iteration with mid-week checks ensures we catch problems early.
- **Customer Involvement**: A Monday demo/call keeps the customer in the loop, allowing rapid backlog adjustments.
- **Mentor Guidance**: Friday calls keep us aligned with university requirements.
- **Team Flexibility**: The GitLab board and label system give us a transparent overview of tasks, priorities, and responsibilities.

---

This **tactical planning** ensures we continuously adapt to changing needs, maintain high code quality via peer reviews, and meet the demands of both the customer and the university throughout the project timeline.