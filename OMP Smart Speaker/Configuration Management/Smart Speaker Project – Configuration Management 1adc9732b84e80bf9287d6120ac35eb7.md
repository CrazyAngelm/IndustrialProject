# Smart Speaker Project – Configuration Management

## 1. Tools Used

- **GitLab (Version Control & CI/CD)**
    
    We store all code, configurations, and scripts in GitLab. Merge requests plus CI pipelines ensure transparent, peer-reviewed changes.
    
- **Notion (Documentation & Change Logs)**
    
    We record configuration decisions, environment setups, and the “why” behind major changes in one place. This centralizes all project knowledge.
    
- **Toggl (Time Tracking)**
    
    By tracking hours on tasks, we identify where the team spends the most effort and spot potential process improvements.
    
- **Miro (Diagramming & Brainstorming)**
    
    We occasionally use Miro to create quick diagrams or flowcharts when discussing architecture or sprint plans.
    
- **Structurizr (C4 Model Diagramming)**
    
    We use Structurizr to store architecture as code, enabling easy modifications and version control.
    

Each tool has a clear purpose. Combined, they keep our configuration process organized, visible to all stakeholders, and easy to maintain.

---

## 2. One-Week Sprint Overview

- **Sprint Length:** Weekly (Saturday to Friday).
- **Key Meetings:**
    - **Saturday (Team Call):** Main planning session to select tasks for the upcoming week, form pairs, and update backlog items.
    - **Monday (Customer Call):** Discuss direction, clarify requirements, align on priorities.
    - **Wednesday (Team Call):** Mid-week check-in to review progress, identify blockers, adjust tasks.
    - **Friday (Mentor Call):** End-of-week demo and feedback.
- **Retrospective:** Briefly documented in Notion at the end of each week, covering what went well, what can be improved, and any action items.

### Example Sprint Timeline

| Day | Activity |
| --- | --- |
| Saturday | Team Call – Sprint planning, backlog refinement |
| Sunday | Wrap up tasks, prepare for sprint |
| Monday | Customer Call – Align on new requirements, set priorities |
| Tuesday | Development in pairs, update GitLab tasks |
| Wednesday | Team Call – Mid-week check, reassign tasks if needed |
| Thursday | Continue development, conduct code reviews and testing |
| Friday | Mentor Call – Demo completed tasks, gather feedback |

This tight weekly cycle ensures continuous alignment, rapid feedback, and quick course corrections.

---

## 3. Task Prioritization

We label tasks **Low**, **Medium**, **High**, or **Critical**, as determined by the project manager based on urgency and impact:

- **Low:** Nice-to-have or long-term ideas.
- **Medium:** Important but not immediately urgent.
- **High:** Significant impact on short-term goals; do soon.
- **Critical:** Immediate priority; takes precedence over all else.

Priorities may shift if new issues arise mid-sprint (e.g., a bug escalates to “Critical”). This keeps everyone focused on what truly matters.

---

## 4. Task Board & Workflow

In Notion, we track tasks through these columns:

1. **Open:** Logged but not in the active sprint.
2. **Not Started:** Planned for the current sprint, work not yet begun.
3. **In Progress:** Actively worked on by the assigned pair.
4. **Review:** Implementation done; awaiting partner check or quick peer review.
5. **Done:** Successfully reviewed and functionally complete.
6. **Closed:** Archived post-sprint (no more action needed).

**Example Flow:** A task goes from **Open** → **Not Started** → **In Progress** → **Review** → **Done** → **Closed**. This board view makes the status of each task clear at all times.

---

## 5. Pair Programming & Task Assignment

- **Pair Work:** Most tasks are handled by two people working closely (sometimes in real-time, sometimes dividing subtasks).
- **Assigning Tasks:** During the Saturday planning call, we decide pairs based on workload and who has the right expertise.
- **Mid-Sprint Adjustments:** If someone is stuck or overloaded, the Wednesday call is our chance to rebalance tasks or bring in a helper.
- **Benefits:** Pairing prevents single points of failure, spreads knowledge, and improves code quality through instant feedback.

---

## 6. Processes

1. **Version Control & Change Management:**
    
    All changes — code or config — must go through a GitLab merge request. This fosters transparency and keeps a detailed log of what changed and why.
    
2. **Deployment & Rollback:**
    
    Every successful GitLab build is packaged. If a release fails on the device, we quickly revert to the last stable commit/tag, minimizing downtime.
    
3. **System Configuration & Environment Management:**
    
    Environment setups (installing dependencies, adjusting OS settings, etc.) are scripted and versioned in GitLab. Any mismatch is either fixed or documented so we maintain consistent setups.
    

---

## 7. Roles & Responsibilities

**Maxim (Product Manager)**

- Maintains the Notion workspace and GitLab task assignments.
- Oversees sprint planning and prioritization to ensure tasks align with project goals.

**Samat (Team Lead)**

- Works closely with Rhasspy tasks; assists with coordination and pair assignments.
- Helps remove blockers during mid-week calls, ensuring the team stays on track.

**Albert (Developer)**

- Focuses on TTS (Text-to-Speech) feature development.
- Collaborates with Philipp for code reviews and ensures smooth integration into the Smart Speaker system.

**Philipp (Developer)**

- Works on Rhasspy tasks alongside Samat; also reviews Albert’s TTS code.
- Provides feedback in merge requests to ensure quality and reliability.

**Igor (Developer)**

- Collaborates on various modules as needed.
- Participates in sprint planning, pair programming sessions, and testing.

All roles share responsibility for keeping tasks updated in Notion, merging code via GitLab, and following our standard processes (e.g., code reviews, environment scripts, time tracking).

---

## 8. Evolution of Our Process – Impact & Benefits

1. **Mid-Week Call Addition**
    - *Before*: Only Saturday (planning) & Friday (demo) calls. Issues surfaced too late.
    - *After*: Introducing Wednesday check-ins helped us catch blockers earlier and rebalance tasks.
    - *Result*: Fewer last-minute crunches, more balanced workload, and better morale.
2. **Refining Task Assignment**
    - *Before*: Some people were underutilized, others overloaded.
    - *After*: Careful Saturday planning ensures each pair has a manageable scope.
    - *Result*: More efficient use of each member’s time, better skill sharing, fewer rollover tasks.
3. **Clearer Task Status & Review**
    - *Before*: Simple “To Do → Doing → Done” often led to tasks marked “Done” without peer checks.
    - *After*: Adding a **Review** column enforces at least one quick verification.
    - *Result*: Higher overall quality, fewer reopened tasks, and greater confidence in final outcomes.

By continuously reviewing what works—and correcting what doesn’t—we stay agile, transparent, and aligned on delivering a solid Smart Speaker solution.

---

# **Document Revision History**

| Version | Date | Comment | Contributor | Task |
| --- | --- | --- | --- | --- |
| v1.0 | 05.02.2025 | Document created | @Альберт Аксёнов  | [https://gitlab.pg.innopolis.university/smart-speaker-group/smart-speaker-codebase/-/issues/45](https://gitlab.pg.innopolis.university/smart-speaker-group/smart-speaker-codebase/-/issues/45) |