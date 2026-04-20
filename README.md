Daily Reflection Tree

Overview

This project implements a deterministic decision tree designed for structured employee reflection. It guides users through predefined questions and reflections without using any AI/LLM.

The system evaluates behavior across three axes:

- Axis 1: Agency (Internal vs External)
- Axis 2: Orientation (Contribution vs Entitlement)
- Axis 3: Radius (Self vs Others)

---

Design Principles

- Deterministic (no randomness, no LLM)
- Fixed-choice inputs only
- Transparent and traceable logic
- Behavior-focused questioning

---

Tree Structure

The tree is implemented as a ".tsv" file.

Each node includes:

- "id", "parentId", "type"
- "text" (display content)
- "options" (for questions)
- "signal" (behavior tracking)

---

Node Types

- start → begins session
- question → user selects option
- decision → routes based on answers
- reflection → insight generation
- bridge → connects axes
- summary → final output
- end → closes session

---

Axes Explained

Axis 1: Agency

Measures whether the user attributes outcomes to internal effort or external factors.

Axis 2: Orientation

Evaluates whether the user focuses on contribution or entitlement.

Axis 3: Radius

Assesses whether the user considers others or remains self-focused.

---

How It Works

1. User answers structured questions
2. Signals are accumulated (e.g., axis1:internal)
3. Decision nodes route flow deterministically
4. Reflection nodes provide insight
5. Summary node synthesizes behavior

---

Why These Questions?

The questions are designed to:

- Reveal attribution patterns (locus of control)
- Identify contribution vs entitlement mindset
- Capture social awareness and team behavior

Each question forces a clear behavioral choice, avoiding ambiguity.

---

Branching Design & Trade-offs

Design Choices:

- Sequential axes (1 → 2 → 3) for clarity
- Binary splits for deterministic routing
- Reflection after each axis for reinforcement

Trade-offs:

- Less flexibility (no free text)
- Simpler logic over deep personalization
- Prioritized clarity over complexity

---

Psychological Basis

The design is inspired by:

- Locus of Control Theory (Internal vs External attribution)
- Prosocial Behavior Theory (Contribution mindset)
- Social Awareness Models (Team vs self orientation)

The goal is not diagnosis, but structured reflection.

---

Tree Diagram (Mermaid)

graph TD
START --> Q1
Q1 --> D1
D1 --> Q1_INT --> R1_INT --> Q2
D1 --> Q1_EXT --> R1_EXT --> Q2
Q2 --> D2
D2 --> Q2_CONTR --> R2_CONTR --> Q3
D2 --> Q2_ENT --> R2_ENT --> Q3
Q3 --> D3
D3 --> Q3_HIGH --> R3_HIGH --> SUMMARY
D3 --> Q3_LOW --> R3_LOW --> SUMMARY
SUMMARY --> END

---

Sample Transcripts

1. High Ownership (Ideal Path)

- Q1: Productive → My effort
- Q2: I helped others → Helping team
- Q3: Helped actively → Team success

Output:
"You demonstrated ownership, contribution, and strong team awareness."

---

2. Low Ownership (Risk Pattern)

- Q1: Stressful → External issues
- Q2: Others didn’t contribute → Unfair treatment
- Q3: Got irritated → Stress

Output:
"You showed external attribution and reactive behavior. Focus on controllables."

---

Key Features

- Fully deterministic
- No AI/LLM usage
- Structured and auditable
- Clear behavior mapping

---

Future Improvements

- Interactive UI (CLI/Web)
- Advanced branching logic
- Behavioral scoring system
- Longitudinal tracking across sessions

---
