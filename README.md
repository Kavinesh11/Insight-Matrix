# Insight-Matrix
# Program-Course Ontology

This ontology models how **Program Outcomes (POs)** and **Course Outcomes (COs)** are related, primarily to support the generation of the **NBA Self-Assessment Report (SAR)**.

We are building this as a **GraphDB-based ontology**, so that we can store, query, and visualize this information easily.

## Main Idea

- A **Program** consists of several **Courses**.
- Each **Course** defines its own **Course Outcomes (COs)** — i.e., what students should achieve after completing that course.
- The **Program** defines a set of overarching **Program Outcomes (POs)** — the higher-level learning goals required for NBA accreditation.

To demonstrate how courses contribute to program outcomes:

- Each **Course Outcome** is linked to one or more **Program Outcomes**.
- This link is modeled via a **Contribution** entity, which stores a **Contribution Strength** — representing *how strongly* a Course Outcome supports a Program Outcome (typically rated 1, 2, or 3).

## Entity Breakdown

- **Program**
    - Contains multiple **Courses**.
    - Has multiple **Program Outcomes**.
- **Course**
    - Belongs to a **Program**.
    - Defines multiple **Course Outcomes**.
    - Stores basic course information:
        - `Course Code`
        - `Lecture Hours`
        - `Tutorial Hours`
        - `Practical Hours`
        - `Credits`
- **Program Outcome (PO)**
    - Represents a high-level learning goal required by NBA.
- **Course Outcome (CO)**
    - Represents a learning objective specific to a Course.
    - Connects to **Program Outcomes** via **Contributions**.
- **Contribution**
    - Links a **Course Outcome** to a **Program Outcome**.
    - Stores the **Contribution Strength** (1 = Low, 2 = Medium, 3 = High).

## Why We Are Doing This

- To clearly document and visualize how **Course Outcomes** contribute to required **Program Outcomes**.
- To simplify the generation of required tables/reports for the **NBA SAR** (especially the CO-PO mapping matrix).

# Workflow diagram initially 

![Screenshot 2025-06-09 224434](https://github.com/user-attachments/assets/cfc9f068-fec2-47e0-84a9-f83f6f8bd4a1)
