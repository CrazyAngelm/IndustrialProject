# Scrum vs. XP for Project Management

# 1. Context

Our team is working on a **proof-of-concept** project to develop a prototype “Smart Speaker” running on an Orange Pi 5 board. The main objectives are:

- Demonstrate **offline (local) voice processing** capabilities
- Verify the concept of a “closed-contour” voice assistant (no constant Internet connection)
- E**xperiment** with relevant technology stacks (TTS/STT, local LLM, etc.)

# **2. Problem Statement**

We need to choose a **lightweight but structured** methodology that allows:

- **Iterative deliveries** (frequent prototypes)
- **Regular communication** with our remote customer and mentor
- An effective way to **estimate and manage** tasks in a small team
- Enough **documentation** to satisfy academic evaluation (yet not overburdening the developers)
- Flexibility for adding or removing features as we experiment with new solutions

The question is: **Should we adopt Scrum or Extreme Programming (XP)** (or a variant) to manage our development process?

# **3. Overview of Options**

## **3.1 Scrum**

### **Summary**

Scrum is an Agile framework typically characterized by fixed-length sprints (1–4 weeks), dedicated roles (*Scrum Master*, *Product Owner*, *Development Team*), and ceremonies such as:

- **Sprint Planning** (define the scope of each sprint),
- **Daily Stand-up** (15-minute daily alignment),
- **Sprint Review** (product demo to stakeholders),
- **Sprint Retrospective** (process improvement discussion).

### **Advantages**

✅ **Clarity & Structure**

Clearly defined events, roles, and artifacts (Product Backlog, Sprint Backlog, etc.).

✅ **Widely Understood**

Many teams are already familiar with Scrum; it is well documented and recognized in academic and professional settings.

✅ **Adaptable**

Teams can reduce ceremony frequency if needed (e.g., fewer daily stand-ups) and still remain “Scrum-like.”

✅ **Separation of Management & Development**

The Product Owner sets priorities, the team delivers increments, and the Scrum Master ensures the process flows.

### **Drawbacks**

‼️ **Ceremonies Might Seem Overkill**

If the team is extremely busy or not co-located, daily stand-ups can be challenging.

‼️ **Requires a Dedicated Product Owner**

Often, the customer or a team member must act as PO, ensuring backlog prioritization. If the customer is less available, the team must fill that gap.

## **3.2 Extreme Programming (XP)**

### **Summary**

XP emphasises best engineering practices (Test-Driven Development, Pair Programming, Continuous Integration, Refactoring) and a very close, **on-site** customer relationship. Iterations are short, and requirements can be changed rapidly.

### **Advantages**

✅ **Engineering Excellence**

Built-in practices (TDD, Pair Programming) can improve code quality, reduce defects.

✅ **Customer Involvement**

With an on-site (or very close) customer, the team quickly clarifies requirements and adapts the solution as needed.

✅ **Frequent Releases**

Encourages small, frequent increments.

### **Drawbacks**

‼️ **Requires Constant Customer Interaction**

Ideally, the customer is physically or virtually “there” every day. Our customer is responsive in chat, but not guaranteed for daily immediate feedback.

‼️ **Mandatory Engineering Practices**

Pair Programming, TDD, and Continuous Integration might be difficult if the team is new to them or has limited capacity to adopt them thoroughly.

‼️ **Less Formal Project Tracking**

XP is usually more about continuous planning than about having a formal plan, which might complicate academic reporting.

# **4. Analysis**

Given our situation:

1. **Team Familiarity**
Some of us have prior experience with Scrum. We know how to conduct Sprint Planning, review, and backlog management. XP’s pair programming and strict TDD are not core practices in our current skill set.
2. **Availability of Customer**
We do have a Telegram channel, but the customer is not embedded in our team daily. He can respond quickly, but not necessarily in “real-time pair” mode. Scrum’s model of a Product Owner with periodic feedback loops seems more natural.
3. **Documentation Needs**
Our university requires a structured plan and explicit tracking. Scrum’s sprint-based approach (with a backlog, story points, sprint reviews) can be documented easily and is straightforward to show on a timeline or Gantt chart.
4. **Team Size**
We are five in total. We can fulfil the “Scrum team” concept (a “Scrum Master/Coordinator,” a pseudo–“Product Owner” role for the backlog, three devs, plus one flexible person), but concept of Pair Programming will be potentially violated. According to the R&D work format it is hard to predict the amount of people, who will actually write the code, so pair programming concept might become impossible to implement.
5. **Engineering Practices**
We want to produce quality code, but we do not necessarily plan on adopting mandatory pair programming or TDD from day one. We might implement some XP-inspired practices (refactoring, short feedback loops) without fully committing to XP later in case of necessity.

# **5. Conclusion & Chosen Approach**

**Decision:** Adopt **Scrum** (with slight modifications to reduce ceremony overhead) as our primary framework.

### **Iterations (Sprints)**

We will run 2-week sprints.

### **Events:**

- **Sprint Planning** (start of each sprint): to select stories, define scope.
- **Asynchronous Stand-ups** (in chat) & short weekly calls: to keep each other updated.
- **Sprint Review & Retrospective** (end of each sprint): to demonstrate our prototype progress, collect feedback from the customer or the mentor, and improve our process.

### **Backlog Management**

A shared Notion containing user stories, technical tasks, and priorities.

### **Product Owner & Roles:**

The customer partially acts as Product Owner by providing priorities and feedback, but if unavailable, the team leads will adjust the backlog.

By following this “Scrum-lite” approach, we will gain:

- **Formal structure** to report to the university (clear sprints, clear tasks, retrospective improvements).
- **Sufficient flexibility** to integrate the customer’s feedback whenever he is available on Telegram.
- A **manageable** set of practices that align with our current skill set and resource constraints.

### **Potential Risks**

- If the customer expects near-instant iteration changes, XP might have been more suitable. However, we believe regular sprint cycles are enough for timely feedback, especially for a proof-of-concept.
- If TDD or pair programming become unexpectedly mandatory, we may need to incorporate more XP practices — but this remains optional unless we see a strong need.

# 6. References

- [https://scrum-master.org/en/extreme-programming-xp-a-beginners-guide-to-the-agile-method/](https://scrum-master.org/en/extreme-programming-xp-a-beginners-guide-to-the-agile-method/)
- [https://www.altexsoft.com/blog/extreme-programming-values-principles-and-practices/](https://www.altexsoft.com/blog/extreme-programming-values-principles-and-practices/)
- [https://fabrity.com/blog/how-to-implement-scrum-in-10-steps/](https://fabrity.com/blog/how-to-implement-scrum-in-10-steps/)
- [https://aws.amazon.com/what-is/scrum/](https://aws.amazon.com/what-is/scrum/)

---

# **Document Revision History**

| Version | Date | Comment | Contributor | Task |
| --- | --- | --- | --- | --- |
| v1.0 | 9.02.2025 | Document created | @Максим Кожинов  |  |