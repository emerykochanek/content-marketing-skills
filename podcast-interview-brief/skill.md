---
name: podcast-interview-brief
description: Build a complete podcast interview brief for 1 IDEA — a show for engineers. Given a transcript, talk, article, guest background, or rough draft questions, produces a documentary-style intro, episode thesis, host overview, 7–10 interview questions, follow-ups, and key host briefing points. Optimized for engineering-leader audiences: CTOs, Staff/Principal Engineers, SRE, Platform, Cloud, FinOps, infrastructure. Use when preparing for a new episode or cleaning up a rough brief.
---

# Podcast Interview Brief — 1 IDEA

## Goal
Turn raw material (transcript, talk, article, guest bio, rough questions, or notes) into a complete episode brief. Every element should serve one sharp thesis — not a broad topic.

The output is:
1. The Idea — one paragraph thesis
2. Documentary-style cold open intro
3. Host overview (key points for Suresh)
4. 7–10 interview questions, with 2–3 marked ★ for strongest
5. 2–3 follow-up probes per top question
6. A cleaned version of any rough draft provided

## The Audience
Engineers, CTOs, VPs of Engineering, SREs, Platform engineers, Cloud engineers, infrastructure leaders, and product-minded engineers. They are skeptical of hype. They respect specificity and mechanism. They do not want to be sold anything.

---

## Step 1: Find the One Idea

Before writing anything, identify the single sharpest claim or tension in the material.

Ask:
- What is the most counter-intuitive thing the guest believes?
- What assumption does this episode challenge?
- What would a senior engineer push back on?
- What decision, failure, or tradeoff does the episode orbit?

The thesis should be specific enough to be wrong. "AI is changing data infrastructure" is not a thesis. "Most teams are optimizing for workloads they'll never have" is.

Write the thesis as a single sentence before doing anything else. If you cannot write it in one sentence, the episode does not have a clear idea yet — keep pulling on the material until it surfaces.

---

## Step 2: Write "The Idea" Paragraph

2–4 sentences. This goes in the host overview and sets up the questions.

Structure:
- Sentence 1: Who the guest is, in terms of what they built or decided — not bio credentials.
- Sentence 2: The core argument they're making today.
- Sentence 3: What the conversation explores — the tension, the mechanism, the implication.

Reference example (Jordan Tigani):
> Jordan helped build BigQuery, one of the defining systems of the big data era. Now he's arguing that most engineers don't actually have a big data problem. The conversation explores how we got here, what assumptions have changed, and how engineers should think differently about architecture going forward.

---

## Step 3: Write the Cold Open Intro

### Structure (PBS / Business Insider cold open)
1. **Concrete surprising fact or tension** — one or two sentences. Not a vague claim. A specific system, decision, cost, or consequence.
2. **The consequence** — what happened as a result. Keep causality explicit.
3. **The contradiction** — the thing that doesn't add up, or the thing the guest now questions.
4. **Introduce the guest** — one sentence. Who they are defined by what they built or decided, not by their title.
5. **Episode question** — the central tension as a direct question or statement.
6. **Standard closer:** "I'm Suresh Mathew, and this is 1 IDEA."
7. **Subscriber ask** (fixed, include verbatim):
   > Before we dive in, quick favor. If you are getting value from this show, please subscribe on YouTube. I get to sit down with the most brilliant engineers I have ever met and just talk shop. No agenda, no marketing. Subscribing tells me it is worth keeping these conversations going and takes five seconds.
8. **Welcome line:** "Welcome to the show, [Guest first name]."

### Rules
- Short sentences. Clear causality.
- No "In today's episode..." or "We get into..."
- No vague phrases: "learned the wrong lesson," "fascinating conversation," "digs deep"
- No guest flattery unless it is tied directly to the thesis
- Do not repeat the episode title more than once
- No marketing language
- The guest introduction should name something they built, shipped, or decided — not their job title

### Reference example (Jordan Tigani):
> Did we overbuild the modern data stack?
>
> BigQuery solved one of the hardest problems in computing: analyzing data at Google's scale. Then everyone else started building like Google.
>
> Jordan Tigani spent more than a decade building BigQuery. Today, he argues that most teams don't actually have Google-scale problems.
>
> I'm Suresh Mathew, and this is 1 IDEA.
>
> Before we dive in, quick favor. If you are getting value from this show, please subscribe on YouTube. I get to sit down with the most brilliant engineers I have ever met and just talk shop. No agenda, no marketing. Subscribing tells me it is worth keeping these conversations going and takes five seconds.
>
> Welcome to the show, Jordan.

---

## Step 4: Write the Interview Questions

### Count and format
7–10 questions. Number them Q1–Q10. Mark the 2–3 strongest with ★.

Strong questions usually do one of:
- Ask for the mechanism: "What are the actual mechanics of how that happens?"
- Ask for concrete costs: "What does that cost operationally and financially?"
- Demand specificity: "Give me something specific."
- Force a tradeoff: "What changes architecturally when…?"
- Name the failure mode: "Where do engineers most often get this wrong?"
- Challenge an assumption: "What assumption no longer holds when…?"
- Ask for a decision framework: "How can teams tell when they're over-engineering?"
- Name a change of mind: "What's the biggest thing you've changed your mind about?"

### Question sequence
- **Q1:** Ground the conversation in the guest's credibility and the core tension. Often sets up the thesis directly.
- **Q2–Q4:** Unpack the mechanism. How did we get here? What does it actually cost? Where does the error happen?
- **Q5–Q7:** The architectural or operational implications. What changes? What should teams do differently?
- **Q8–Q9:** The forward-looking angle — usually AI, org change, or a shift in assumptions.
- **Q10:** The reflective close — what has the guest changed their mind about, or what would they do differently?

### Questions to avoid
- "Tell me about your journey" or "How did you get here?"
- "What excites you about this space?"
- "What should listeners take away?"
- "What is the future of X?" — too broad; reframe as a specific mechanism or decision
- Questions that restate the topic without adding tension

### When a draft question is weak
Replace vague phrases with specific mechanisms:
- "learned the wrong lesson from this" → "what specific assumption did the industry import from [X] that doesn't apply to most teams?"
- "opposite premise" → "what does an architecture built on [specific assumption] actually look like, and where does it break?"
- "future of data engineering" → "as AI agents become a major consumer of data pipelines, what does a data engineer actually own?"
- "what does this mean for engineers" → "what does a team have to change architecturally when they accept this?"

### Follow-up probes
For the ★ questions, provide 2–3 follow-up probes. These are shorter — used when the guest gives a high-level answer and needs to be pushed for specifics.

Examples:
- "Can you give me a specific example of that?"
- "What does that actually look like in a real system?"
- "What's the cost when teams get that wrong?"
- "Where does that break down?"
- "Is that a technical constraint or an org constraint?"

---

## Step 5: Write the Host Overview

Bullet list of 3–7 key points for Suresh to have in his head going into the interview.

Rules:
- Each bullet is a fact, claim, or tension — not a topic label
- Include the guest's most provocative claim
- Include the assumption being challenged
- Include any surprising number, scale claim, or concrete mechanism
- The last bullet should be the central question that the episode is organized around

Reference example (Jordan Tigani):
- Jordan spent more than a decade building BigQuery at Google, helping create one of the systems that defined the modern data stack.
- His core argument: most companies adopted architectures built for Google-scale problems, even though most workloads are small enough to fit on a single machine.
- He believes the industry conflated "big data" and "big compute." They are different problems, and treating them as the same led to unnecessary complexity across modern analytics infrastructure.
- One of his most provocative claims: most teams are optimizing for a future scale they'll never reach instead of the workloads they actually have.
- Jordan argues that the next big infrastructure shift won't come from larger datasets. It will come from AI agents becoming a massive new consumer of data and analytics systems.
- His rule of thumb: design for the primary use case, not the corner case.
- The question underlying the entire conversation: Did we overbuild the modern data stack?

---

## Output Format

Deliver the brief in this order:

```
## Topic
[Short topic label]

## The Idea
[2–4 sentence paragraph]

## Intro
[Full cold open, including subscriber ask and welcome line]

## Host Overview
[3–7 bullet points]

## Questions
Q1. [question]
Q2. [question] ★
...

### Follow-up probes for ★ questions
Q[N]:
- [probe 1]
- [probe 2]
- [probe 3]
```

If the user provides a rough draft, also include a **Cleaned Draft** section at the end showing the revised version of each question they submitted, with a one-line note on what changed and why.

---

## Keeping the Episode Focused

After completing the draft, do a single focus check:

- Does every question connect back to the one thesis?
- Are there any questions that would work on any podcast about any engineer? (If yes, cut or sharpen.)
- Is there a question that only this guest, with this background, can answer? (If not, add one.)
- Is the intro answerable from the intro alone, without having heard the episode?

If any of these fail, revise before outputting.

---

## Style Rules

- Direct, smart, and conversational — not academic, not marketing
- Short sentences in the intro
- Questions should have tension built in, not neutral framing
- The host briefing is for Suresh — written as facts he'd want to know before sitting down, not as podcast copy
- Default to a 30-minute interview arc unless the user specifies otherwise
- Do not editorialize about the guest's career or trajectory unless it directly serves the thesis
