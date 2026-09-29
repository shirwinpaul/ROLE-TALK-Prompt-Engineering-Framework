# ROLE TALK Framework

**A prompt engineering framework for role-adaptive knowledge delivery through LLMs.**

Created by **A. Shirwin Paul Akilan** © 2026. All rights reserved unless otherwise licensed below.

---

## What is ROLE TALK?

ROLE TALK is a prompt framework designed for one specific purpose: helping a person learn *new* information — trivia, history, general knowledge, facts — from an LLM in a way that is shaped by **who they are**, not just **what they ask**.

Unlike quiz-style or Q&A-loop frameworks, ROLE TALK does not test the learner. It functions like a **tailored encyclopedia**: the learner states their Role, Topic, Aim, Level, and Know-how once, and the LLM responds with a single rich, accurate, well-structured answer — calibrated to that exact person.

### Why it's different

Most learning-oriented prompt frameworks assume one of two things:
1. Every learner at "beginner" level wants shallow content, or
2. The best way to teach is to quiz and correct.

ROLE TALK rejects both assumptions:
- **Beginners are not restricted to shallow depth.** A first-time learner can request expert-level detail if they want it.
- **The same topic should read differently for different people.** An IAS exam aspirant and a school quiz-competition student asking about "Indian Freedom Movement" should not receive the same answer — ROLE TALK's Role field ensures the content itself adapts, not just the tone.

---

## The Five Fields

| Letter | Field | Definition |
|---|---|---|
| **R** | **Role** | Who the person is in relation to the topic (e.g., IAS aspirant, school quiz competitor, professional, hobbyist). Determines *what kind* of facts and framing are relevant. |
| **T** | **Topic** | The specific subject the person wants to learn about. |
| **A** | **Aim** | The purpose behind learning it (e.g., exam prep, curiosity, competition, professional need). |
| **L** | **Level** | The person's current familiarity with the topic. |
| **K** | **Know-how** | How deep the person wants the answer to go — from a quick overview to expert-level depth. *Never restricted by Level.* |

---

## How It Works

1. **Intake** — The LLM collects all five fields conversationally, in natural language, using the framework's own vocabulary (Role, Aim, Level, Know-how). If the learner provides some fields upfront, the LLM asks only for what's missing.
2. **Delivery** — Once all five fields are known, the LLM produces one comprehensive, encyclopedia-style response: trivia, history, and general knowledge on the Topic, filtered and framed through the person's Role, Aim, Level, and Know-how.
3. **No quiz loop** — ROLE TALK does not test or score the learner. The value is in the tailored delivery of information itself.

---

## Prompt Template

```
You are operating under the ROLE TALK framework, a knowledge-delivery
method with five fields: Role, Topic, Aim, Level, Know-how.

If any field below is missing, ask the learner for it conversationally,
using these exact field names, before answering.

Role: {ROLE}
Topic: {TOPIC}
Aim: {AIM}
Level: {LEVEL}
Know-how: {KNOW_HOW}

Once all five fields are known, respond with a single rich, accurate,
well-organized answer covering relevant trivia, history, and general
knowledge on the Topic. Tailor the content itself — not just the tone —
to the person's Role and Aim. Match the requested Know-how depth
regardless of their Level; a beginner may request expert-level depth.
Do not quiz, test, or ask the learner questions after this point unless
they explicitly request it.
```

---

## Intake Script (Reference Example)

**When Topic is given but other fields are missing:**

> "Understood — I'll help you explore **[Topic]**. A few quick details will help me tailor this properly:
> - **Role** — your role or background in relation to this topic
> - **Aim** — your purpose in learning this
> - **Level** — how familiar you already are with it
> - **Know-how** — how deep you'd like this to go
>
> A brief answer to each is enough."

**When some fields are already given:**

> "Thank you — I have your [fields already provided]. Could you also share your [missing fields]?"

**Fallback, if Level is unknown or declined:**

> "No problem — I'll start from the fundamentals and build up, while still matching the depth you asked for."

---

## Worked Example

**Input:**
- Role: School student preparing for quiz competitions
- Topic: The Indian Space Programme
- Aim: Competitive quiz prep
- Level: Knows the basics (ISRO, Chandrayaan)
- Know-how: Deep — wants lesser-known facts too

**Output (abridged):**
> A well-organized answer covering ISRO's founding, major missions (Aryabhata, Chandrayaan, Mangalyaan, Gaganyaan), plus quiz-friendly details: firsts, records, dates, and obscure facts likely to appear in competitions — framed for rapid recall rather than academic depth.

**Same Topic, different Role (IAS aspirant, Aim: UPSC GS paper):**
> The same core facts, but reframed around policy relevance, funding and governance structure of ISRO, India's space policy 2023, and international collaborations — content an IAS aspirant would actually be tested on.

This side-by-side is the core proof of concept: same Topic and Know-how, different Role and Aim, materially different output.

---

## Attribution & License

**Framework author:** A. Shirwin Paul Akilan, Madurai, Tamil Nadu, India
**Created:** 2026

This work is licensed under **CC BY 4.0** — you may share and adapt this framework for any purpose, including commercially, as long as appropriate credit is given to the original author.

To cite:
```
Akilan, A. Shirwin Paul. "ROLE TALK: A Role-Adaptive Prompt Framework 
for Knowledge Delivery." 2026.
```

---

## Status

This is version 1.0 — the framework has been designed and specified but not yet tested across multiple LLMs. Testing and refinement notes will be added as the framework develops.
