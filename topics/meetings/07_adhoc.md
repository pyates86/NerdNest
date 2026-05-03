# Chapter 07: Ad-hoc & High-Stakes Meetings

In a perfect world, every meeting would be scheduled two weeks in advance with a pristine agenda. In reality, engineering is chaotic. Servers go down, critical bugs are discovered, and creative deadlocks happen. **Ad-hoc meetings** are the "Emergency Response" of your team. Because these sessions are often high-stress, having a clear protocol is the only thing that prevents them from devolving into panic.

---

## 7.1 The War Room (Incident Response)
When a P0 (Priority 0) incident occurs, the team enters "Incident Command" mode.

* **The Trigger:** A monitoring alert or a massive surge in error logs.
* **The Protocol:**
    * **The Lead:** One person is the "Incident Commander." They are the only one who makes final decisions.
    * **The Comm:** One person handles stakeholder communication so the engineers can focus on the fix.
    * **The Rule:** No blaming. Focus entirely on **Mitigation** (stopping the bleeding) first, then **Remediation** (fixing the wound).

---

## 7.2 The Post-Mortem / Root Cause Analysis (RCA)
Once the fire is out, you meet to ensure it never happens again. This is the most high-stakes "Learning Meeting" an engineer will attend.

* **Blameless Culture:** We assume the failure was systemic, not personal. (e.g., "Why did the system allow a dev to push code that crashed the DB?" instead of "Why did Dave push that code?").
* **The Output:** A list of "Action Items" to harden the system.
* **The Timeline:** A chronological reconstruction of exactly what happened, when it was detected, and when it was resolved.

---

## 7.3 The Brainstorming "Jam" Session
Sometimes the team is stuck on a difficult architectural problem. You need a "Whiteboard Session."

* **The Goal:** Divergent thinking (generating many ideas) followed by Convergent thinking (picking the best one).
* **The Protocol:** * **No "Bad Ideas" Phase:** For the first 15 minutes, criticism is banned.
    * **Visual First:** If you aren't drawing, you aren't brainstorming.
    * **The Decision Maker:** End the meeting by identifying who has the "Final Say" so the session doesn't end in a stalemate.

---

## 7.4 Conflict Resolution / Mediated Meetings
When two senior devs have fundamentally different views on a technical direction, or when interpersonal friction stalls the team, a mediated meeting is required.

* **The Third Party:** Usually a Manager or a neutral Lead Engineer.
* **The Structure:** 1.  Person A presents their view (uninterrupted).
    2.  Person B presents their view (uninterrupted).
    3.  Find the **Shared Goal** (e.g., "We both want the app to be secure").
    4.  Negotiate the trade-offs.

---

## 7.5 Managing the "Interrupt"
Ad-hoc meetings are the ultimate "Context Switch." To protect the team:
* **Assess Urgency:** Ask, *"Does this need a meeting right now, or can it wait for a Sidebar after tomorrow's Stand-up?"*
* **Small Blast Radius:** Only pull in the people absolutely necessary to resolve the crisis. Don't pull the whole team into a War Room unless the whole system is down.

---

## 🛠 Hands-on: The "RCA" Roleplay
Think of a minor bug or "near-miss" that happened recently.
1.  **Run a Mini-RCA:** Ask the "Five Whys" (from Soft Skills Chapter 05).
2.  **Draft one "Systemic Fix":** Instead of saying "I'll be more careful," suggest a technical guardrail (e.g., "I will add a linting rule to prevent this specific syntax").
3.  **Reflect:** Notice how much more productive it feels to blame the *process* rather than yourself.

---

**Next Up:** To master these sessions, you need the right tools in your belt. In **Chapter 08: Meeting Resources**, we provide templates and checklists to help you facilitate like a pro.
