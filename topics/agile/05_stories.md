# Chapter 05: User Stories & Requirements

In Agile, we don't write 50-page technical specifications that no one reads. Instead, we use **User Stories**. A User Story is a small, high-level description of a feature, told from the perspective of the person who desires the new capability. It shifts the focus from writing about requirements to *talking* about them.

---

## 5.1 The User Story Formula
A standard user story follows a specific template to ensure that the **Who**, **What**, and **Why** are always clear:

> **As a** [type of user],  
> **I want** [some goal/action],  
> **So that** [some reason/benefit].

* **Example:** "As a premium subscriber, I want to download songs for offline listening so that I can enjoy music without an internet connection."

---

## 5.2 The 3 C's of User Stories
Coined by Ron Jeffries, this framework describes the components of a story:
1.  **Card:** The written description (often on a Jira ticket or physical index card). It is an invitation to a conversation.
2.  **Conversation:** Discussions between the team and the Product Owner to flesh out the details.
3.  **Confirmation:** The **Acceptance Criteria** that prove the story is finished and working as intended.

---

## 5.3 The INVEST Criteria
How do you know if a story is "good"? It should follow the INVEST mnemonic:

* **I - Independent:** It should be able to be developed/deployed without being tightly coupled to another story.
* **N - Negotiable:** It’s not a contract; the details are worked out during the "Conversation."
* **V - Valuable:** It must deliver clear value to the end user or the business.
* **E - Estimable:** The team must understand it well enough to provide a rough size/effort estimate.
* **S - Small:** It should fit within a single sprint (if it's too big, it's an **Epic**).
* **T - Testable:** There must be a way to verify that it works.



---

## 5.4 Acceptance Criteria (AC)
While the Story describes the intent, the **Acceptance Criteria** describe the boundaries. These are the specific conditions that a software product must meet to be accepted by a user or customer.

**Example ACs for a Login Story:**
* User is redirected to the dashboard after a successful login.
* An error message appears if the password is incorrect.
* The account is locked after 5 failed attempts.
* The password field is masked (dots/asterisks).

---

## 5.5 Epics and Spikes
* **Epic:** A large body of work that can be broken down into many smaller stories. (e.g., "Implement User Authentication").
* **Spike:** A special type of story used for research or exploration. If the team doesn't know *how* to build something, they create a Spike to figure it out before committing to a regular story.

---

## 🛠 Hands-on: Writing Your First INVEST Story
Think of a simple feature you want to build (e.g., a "Dark Mode" toggle).
1.  **Draft the Story:** Write it using the "As a... I want... So that..." format.
2.  **Add 3 ACs:** What are the three things that *must* happen for this to be "Done"?
3.  **The INVEST Audit:** Is your story too big? Is it testable? If you can't think of how to test it, the story needs to be rewritten.

---

**Next Up:** Once we have our stories, we need to decide how long they will take to build. In **Chapter 06: Estimation & Velocity**, we'll learn why we use "Story Points" instead of "Hours."
