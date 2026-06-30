---
name: one-idea-youtube-packager
description: Create YouTube packaging for 1 IDEA podcast episodes from a transcript. Produces title options, thumbnail options, description, and chapters. Includes SEO research, engineer community language research, and thumbnail visual direction. Output is a scored report on each option plus a final recommended package. Optimized for AI, cloud, DevOps, SRE, platform engineering, FinOps, and infrastructure audiences.
---

# 1 IDEA YouTube Packager

## Goal
Turn an episode transcript into a complete YouTube package: title, thumbnail, description, and chapters.

The output is a report with scored options for title and thumbnail, then a final recommended package built around the best choice.

Everything should read like an engineer wrote it — not a marketer, not a copywriter, not an AI assistant.

---

## The Audience
Staff and Principal Engineers, CTOs, VPs of Engineering, DevOps, SRE, Platform, Cloud, FinOps, infrastructure engineers. They are skeptical. They skip anything that sounds like a webinar or a vendor pitch. They click on things that name a real problem they've run into.

---

## Working Process

### Step 1: Read the Full Transcript

Before writing anything, read the entire transcript and identify:

- What does the guest keep coming back to? That's the thesis.
- What is the single sharpest, most concrete claim in the episode?
- What failure mode, mistake, or tradeoff does the episode actually explain?
- What would a senior engineer push back on or forward to their team?

Write the thesis in one sentence before doing anything else. If you can't, the episode doesn't have a clear enough angle yet — keep pulling on the transcript until it surfaces.

The thesis should be specific enough to be wrong. "AI is changing cloud infrastructure" is not a thesis. "Most cloud optimization tools labeled autonomous are running if-statements, not intelligence" is.

---

### Step 2: SEO Research

Before writing titles, identify what engineers are actually searching for. The goal is to find the overlap between what the episode covers and what people search for.

**Run searches on:**
- The core topic (e.g. "cloud cost optimization tools," "kubernetes autoscaling failure," "AI in production")
- The failure mode the episode describes (e.g. "cloud optimizer outage," "automated system took down production")
- Related practitioner complaints (e.g. "overprovisioned kubernetes," "cloud waste")

**Look for:**
- Which exact phrases appear in high-ranking articles, forum posts, and comparison guides
- Whether the topic is searched as a problem ("why does X fail") or a solution ("best X tool")
- What language engineers use vs. what vendors use — they are often different

**Avoid:**
- Targeting phrases with no search volume just because they sound right
- Using vendor or analyst language that practitioners don't actually use
- Broad category terms ("AI," "cloud," "DevOps") without a specific angle

**Output of this step:** a short list of 2–4 keyword phrases with actual search demand that can anchor the title and description.

---

### Step 3: Engineer Language Research

Before writing copy, find out how practitioners actually talk about this topic — not how vendors or analysts frame it.

**Search:**
- Reddit communities (r/devops, r/sre, r/kubernetes, r/aws, r/finops, r/MachineLearning, r/ExperiencedDevs)
- Hacker News discussions on the topic
- Engineering blog post titles and comment sections
- Post-mortem write-ups if the episode covers a failure mode

**Look for:**
- The specific words engineers use when they're frustrated with this problem
- Phrases that appear repeatedly across different engineers (not just one post)
- What engineers call the thing the episode is about — it often differs from the formal/vendor term
- Any counter-intuitive takes that get a lot of engagement

**What this changes:** Titles, description language, chapter labels, and thumbnail text should use the words engineers actually use, not the polished version.

Example: Engineers say "took down production," "got paged at 3am," "burned by it," "went back to doing it manually," "AI washing" — use that language, not "impacted availability" or "suboptimal outcomes."

---

### Step 4: Find the Thumbnail Quote

Before anything else, find the single most provocative short quote from the guest in the transcript. This is the primary thumbnail option for every episode.

**What you're looking for:**
- 3–6 words, spoken directly by the guest
- Surprising, contrarian, or something an insider wouldn't normally say out loud
- Creates a cliffhanger — the viewer needs context to understand why they said it
- Works without the episode title to explain it

**Good examples:**
- "I blame Google" — ex-BigQuery engineer on why teams over-built data infrastructure
- "I Ship Code I Don't Read" — founder on AI-generated code
- "I blame Google" works because it's short, provocative, and from someone with standing to say it

**How to find it:**
- Scan for moments where the guest says something that sounds like it came out of nowhere
- Look for self-aware confessions, strong opinions, or counterintuitive takes
- The best quotes often start with "I," "We," or name a specific company or technology

**The thumbnail format (follow this exactly):**
- Guest face, black and white photo
- Quote in large bold text with quotation marks
- Guest name + title + company in small text underneath, with an arrow pointing to their face
- Dark background or high contrast

**If no strong quote exists**, fall back to the episode topic in bold (e.g. "Why Most Teams Don't Need BigQuery") with the same face + credential format.

**Output of this step:** The best quote pulled directly from the transcript, plus one fallback option.

---

### Step 5: Generate Title Options

Use the thesis, the SEO research, and the engineer language research to generate 4–5 title options.

**Each title should:**
- Use the exact search phrases engineers use (from Step 2 and Step 3)
- Promise something the episode actually delivers — not a tangential point
- Be readable as a YouTube title: direct, specific, no setup required
- Be under 65 characters when possible

**Title patterns that work for this audience:**

- Names the failure: *Why Cloud Optimizers Keep Taking Down Production*
- Names the lie: *Why Most Cloud Cost Tools Are Lying to You*
- Names the mistake: *The Cloud Optimization Mistake That Costs More Than It Saves*
- Names the gap: *Your Cloud Optimizer Is Running Rules, Not Intelligence*
- Stakes + specificity: *We Lost 40% Cloud Spend to a Tool That Claimed to Be Autonomous*

**Avoid:**
- Vague mystery titles: *The Problem No Optimizer Can Solve*
- Abstract claims: *Autonomy Is the Future*
- Overpromising: only use a claim if the episode actually covers it in depth
- Cute wordplay or puns
- Question titles unless the episode directly answers a question engineers are already asking

---

### Step 6: Score the Title Options

For each title, score it on three dimensions:

**Clickability (1–5):** Would an engineer scroll past this or stop?
- 1 = generic, no tension
- 3 = interesting but not urgent
- 5 = names a real problem they've experienced

**SEO fit (1–5):** Does it use phrases engineers actually search?
- 1 = no searchable terms
- 3 = adjacent terms, not exact
- 5 = exact phrases with real search demand

**Search intent match (1–5):** Does it target the right moment in the engineer's journey?
- 1 = wrong audience or wrong moment
- 3 = broad, multiple interpretations
- 5 = targets engineers at exactly the moment they'd watch this (evaluating tools, recovering from an incident, etc.)

Add a one-line note on why each score is what it is.

---

### Step 7: Generate Thumbnail Options

Produce 3 thumbnail directions. Each should include:

- **Text (if any):** 0–4 words max. Short enough to read on a phone.
- **Visual concept:** One sentence describing what's in the frame.
- **Why it works:** One sentence.

**Good thumbnail text examples:**
- IT'S JUST RULES
- NOT AUTONOMOUS
- BROKEN BY DESIGN
- YOU'RE OVERPAYING
- IT LIED

**Avoid:**
- Text that repeats the title
- More than 4–5 words
- Vague labels like "THE TRUTH" or "WATCH THIS"
- Technical diagrams that require zooming in

**Score each thumbnail on:**
- Mobile readability (1–5): Is it clear on a 4-inch screen?
- Adds to the title (1–5): Does it say something the title doesn't?
- Audience fit (1–5): Would a senior engineer find this credible, not clickbait-y?

---

### Step 8: Write the Description

**Format — follow this exactly:**

1. **One sentence.** Who the guest is and what they argue. Specific, no setup.
2. **One sentence.** "On this episode of 1 IDEA, [Guest Name] ([Title] @ [Company]) breaks down [topic 1], [topic 2], and [topic 3]."
3. **"We cover:" bullet list.** 4 bullets max. Short, direct, no punctuation at the end of each line.

That's it. No extra paragraphs. No openers. No closers. No "In this episode."

**Example (use this as the exact model):**

> Jordan Tigani spent over a decade at Google building BigQuery. Now he argues most companies adopted it for a scale they will never reach, and that AI agents are exposing exactly what that cost.
>
> On this episode of 1 IDEA, Jordan Tigani (Co-Founder & CEO @ MotherDuck) breaks down the big data myth, why query latency matters more than throughput for agents, and what data engineers should actually be building for now.
>
> We cover:
> - Why most teams adopted Google-scale infrastructure they never needed
> - Why AI agents need query latency, not throughput
> - How AI is collapsing the modern data stack
> - Why data engineers become more valuable in the AI era

**Writing rules:**
- No AI-sounding phrases: "delve into," "crucial," "landscape," "paradigm," "holistic," "leverage," "unpack," "dive deep"
- No marketing language: "cutting-edge," "best-in-class," "game-changing," "innovative"
- No questions that start the description
- No vague stakes ("this is more important than ever")
- Write like you're telling a colleague what the episode is about

---

### Step 9: Write the Chapters

Chapters are what engineers click when they want to jump to a specific part. Write them like a table of contents for a technical post, not a podcast summary.

**Rules:**
- Use actual timestamps from the transcript
- Each chapter should describe what an engineer learns at that point, not what the speakers talk about
- Title case, plain language
- No AI-grammar phrasing: "Exploring," "Understanding," "Unpacking," "The Journey"
- No vague labels: "Discussion," "More Details," "Continued," "Final Thoughts"
- Keep each chapter under 50 characters
- The first chapter is always 0:00 — Introduction

**The rule:** Short enough to scan, specific enough that you know exactly what's being discussed. Always name the specific technology, company, or argument — not a vague concept.

**Good examples:**
- Why Google's Architecture Spread Everywhere
- Most Companies Don't Actually Have Big Data
- The Cost of Running BigQuery You Don't Need
- Big Data vs Big Compute
- How BigQuery Optimizes for Throughput, Not Latency
- Who Profits From the Big Data Myth
- Why Engineers Still Believe the Big Data Myth
- Why AI Agents Need a Different Query Engine
- The Data Engineer's Role in an AI World

**Bad examples (too vague — these tell you nothing):**
- The Big Data Myth
- Why Teams Over-Built
- The Real Cost
- Why It Stuck
- What Data Engineers Should Do Now
- Who Benefits

**Bad examples (too cute — name a concept instead of making a point):**
- BigQuery Was Actually Two Products
- The Journey to MotherDuck
- Exploring the Data Stack
- Understanding Trust
- Wrapping Up

**The test:** Read the chapter title in isolation. Can you tell what technology or argument is being discussed? If not, it's too vague. Does it sound like a podcast summary instead of a table of contents? If so, rewrite it.

---

## Output Format

Deliver in this order:

---

### Episode Thesis
[One sentence. The core argument. Specific enough to be wrong.]

---

### SEO Keywords Found
[2–4 phrases with real search demand. Note whether each is high/medium/low volume and what intent it targets.]

---

### Engineer Language Notes
[3–5 phrases practitioners actually use about this topic. Where you found them.]

---

### Title Options

For each title:

**Title:** [title]
**Clickability:** [X/5] — [one-line reason]
**SEO fit:** [X/5] — [one-line reason]
**Search intent:** [X/5] — [one-line reason]
**Why it's strong / what it risks:** [2–3 sentences]

---

### Thumbnail Options

For each thumbnail:

**Text:** [0–4 words or "no text"]
**Visual:** [one sentence]
**Mobile readability:** [X/5]
**Adds to title:** [X/5]
**Audience fit:** [X/5]
**Why it works:** [one sentence]

---

### Recommended Package

**Title:** [final title]
**Thumbnail text:** [text or "no text"]
**Thumbnail visual:** [one sentence]

**Description:**
[Full description. Three paragraphs max before "Today on 1 IDEA." 2 sentences each.]

Today on 1 IDEA, [keep this section in the established format]

**Chapters:**
[Timestamp — Chapter Title]

---

## Quality Check

Before finalizing, verify:

- The title matches the whole episode, not one segment
- Every claim in the description is backed by the transcript
- No AI-sounding phrases or marketing language anywhere in the copy
- Chapters are jump points, not summaries
- The thumbnail text is readable at phone size
- The description opener names the problem in plain language without setup
- The package would be credible to a Staff Engineer or VP Eng who is skeptical of hype
