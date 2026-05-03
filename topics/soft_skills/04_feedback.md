# Chapter 04: Giving & Receiving Feedback

In software engineering, feedback is the high-frequency signal that keeps a project on course. Without it, you are flying blind. Whether it is a code review, a 1:1 with a manager, or a post-mortem after a server crash, the ability to process feedback determines how fast you—and your team—can iterate and grow.

---

## 4.1 The Feedback Loop
Think of feedback as a **Control System**. 
* **The Input:** Observations about behavior or code.
* **The Process:** Evaluation and communication of that input.
* **The Output:** A change in behavior or an optimization of the product.

If the "sensor" (the person giving feedback) is noisy or the "receiver" (the person getting feedback) has high resistance, the system becomes unstable.

---

## 4.2 Giving Feedback: The SBI Model
Engineers often give vague feedback like "This code is bad" or "You need to be more proactive." This is unhelpful and triggers defensiveness. Instead, use the **Situation-Behavior-Impact (SBI)** model:

1.  **Situation:** Define the "when" and "where." (*"During this morning's stand-up..."*)
2.  **Behavior:** Describe the observable action, not the person's character. (*"...you interrupted Sarah three times while she was explaining the API change..."*)
3.  **Impact:** Explain the result of that behavior. (*"...it made it difficult for the team to understand the technical requirements and Sarah stopped sharing her ideas."*)

---

## 4.3 Receiving Feedback: Managing the "Defensive Flush"
When you receive criticism, your brain’s amygdala often triggers a fight-or-flight response. Your heart rate rises, and you stop listening. To handle this:

* **Listen to Understand, Not to Rebut:** Don't start building your "defense case" while they are still talking.
* **The "Tell Me More" Protocol:** If feedback feels vague or unfair, don't argue. Ask for examples: *"Can you help me understand where you saw that happening so I can fix it?"*
* **Separate Your Self-Worth from Your Code:** A "Request for Changes" on a Pull Request is not an attack on your intelligence; it is a collaborative effort to improve the product.

---

## 4.4 Radical Candor
The goal for an engineering team is **Radical Candor**: the intersection of **Caring Personally** and **Challenging Directly**.



* **Obnoxious Aggression:** Challenging without caring (the "brutally honest" dev who is just being mean).
* **Ruinous Empathy:** Caring without challenging (letting a peer ship bad code because you don't want to hurt their feelings).
* **Manipulative Insincerity:** Neither caring nor challenging (backstabbing or silence).
* **Radical Candor:** Telling the hard truth because you want your teammate to succeed.

---

## 🛠 Hands-on: Refactoring a Feedback Statement
Take the following "Obnoxious Aggression" statement and refactor it into an **SBI** statement with **Radical Candor**:

* **Original:** "Your documentation is lazy and confusing. No one knows how to use this service."
* **Refactored (Your turn):** Think about a specific situation (a meeting or a ticket), a specific behavior (missing examples or broken links), and a specific impact (onboarding time or bugs).

---

**Next Up:** Feedback only works if people do what they say they will do. In **Chapter 05: Importance of Accountability**, we will explore how to build the "Trust Infrastructure" of a team through ownership.
