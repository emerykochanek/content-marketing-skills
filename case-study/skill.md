---
name: case-study
description: Full-lifecycle B2B case study producer. Given a customer name, context, or raw interview transcript, runs the complete workflow: pre-interview question set, PSR-structured draft, sales enablement tagging, and multi-channel distribution plan. Use when the user wants to create, draft, or plan a case study, build a proof library, or scale case study production. Optimized for B2B SaaS companies with sales-led GTM motions.
---

# Case Study Skill

## Required: Load Sedai Messaging Docs First

**Before writing or reviewing any case study, always retrieve and read these files from Google Drive.** They are the source of truth for brand voice, positioning, value drivers, differentiators, and terminology. Do not rely on memory — fetch them fresh each time.

| Doc | Google Drive File ID | What it governs |
|---|---|---|
| Messaging Guide | `1fM5JwpLM1WbTedVgVIS1zXsZOtaupzNq` | Brand voice, tagline, core messaging, style rules, terminology (e.g. never use "automation" for Sedai — always "autonomous") |
| Value Selling Framework | `1Z8Oq42F8R8kvS6G_-XdkRBaxQA0P3Lgd` | Three value drivers, before/after scenarios, proof points, differentiators |
| Buyer Personas | `1eGt8_-outfFwtoVAIbobLABf6Yr4uKtP` | ICP titles, pain points, objections — use to match case study angle to the right persona |
| Every Meeting Deck | `1Y8v7o1ggt-yq4gGaCbHAvqIgrSh1H5pW` | Core narrative arc, competitive positioning, proof point format |

All four files live in the **Master Messaging Docs** folder (Drive folder ID: `1lwzynMOHAHdF8CdRceHjiXQFfrvJW2iu`).

Use the `mcp__6936595a-44d7-4b3d-a7c9-b3bfbbe33030__read_file_content` tool with the file IDs above to fetch them. If a file fails to load, flag it and proceed with the others.

### Key rules pulled from these docs (always verify against the live files):

- **Never use "automation" or "automated" when referring to Sedai** — use "autonomous" or "autonomously." Automation is the villain in Sedai's narrative (blind, risky automation). This is a hard rule.
- **Customer is always the hero** — Sedai is a supporting character, not the subject of the story.
- **Tagline:** "The self-driving cloud.™" — add ™ on first use only.
- **The three value drivers** every case study should map to: (1) Reduce cloud costs without compromising performance, (2) Deliver exceptional user experience through high-performing, reliable apps, (3) Eliminate manual toil to boost engineering productivity.
- **The five core differentiators:** Application-Aware Intelligence, Outcome-Driven Optimization, Safe Autonomy, Full-Stack Cloud Coverage, Enterprise-Grade Governance.
- **Brand voice:** Friendly Rebels — honest, approachable, customer-centric, unique, confident, revolutionary.

---

## What This Skill Does

Runs the complete case study lifecycle in one pass:

1. **Pre-interview brief** — tailored questions to surface the right metrics, story, and quotes
2. **Structured draft** — PSR format optimized for conversion and credibility, aligned to Sedai messaging
3. **Sales enablement tags** — metadata so reps can find and use the right study at the right moment
4. **Distribution plan** — channel-by-channel repurposing guide

Input can be any of:
- Customer name + product context + known outcome (→ generates questions and outline)
- Raw interview transcript or notes (→ drafts the full case study)
- Completed draft (→ adds sales tags and distribution plan)

Read the user's input and determine which phase to start from. If input is sparse, start with the interview brief and ask for what's missing.

---

## Phase 1: Pre-Interview Brief

When the user has a customer but no transcript, produce a tailored interview brief.

### Context to gather first
Before writing questions, confirm (ask if not provided):
- What product/feature did the customer use?
- What is the primary outcome already known (if any)?
- What positioning claim should this case study prove? (e.g., "customers reduce costs without touching code," "time-to-value under 30 days," "works without needing a dedicated team")
- What is the customer's industry, company size, and ICP fit?

### The Interview Question Framework

Structure questions in five groups. Use 2–3 questions per group — do not send all of them. Pick the most relevant based on context.

**Group 1: Before State (the problem)**
> Goal: surface a specific, named pain — not category language.

- "Before you started using [product], what was the problem you were trying to solve? Can you give me a concrete example of when it was painful?"
- "How were you handling [problem area] before? What was the process?"
- "What was the business cost of not solving this — lost time, missed SLAs, extra headcount, risk?"
- "What had you tried before that didn't work, and why?"

**Group 2: The Decision (why us)**
> Goal: capture selection rationale — the most-skipped credibility signal.

- "What made you decide to try [product]? What were the alternatives you considered?"
- "What was the deciding factor? Was there a specific moment or proof point that tipped it?"
- "What were you skeptical about before starting?"

**Group 3: Implementation (the journey)**
> Goal: make the story real and specific. Remove vendor-hero framing.

- "Walk me through what the first 30/60/90 days looked like."
- "Was there anything harder than expected? How did you work through it?"
- "Who on your team was involved and how did their role change?"

**Group 4: Results (the proof)**
> Goal: force specificity. Vague outcomes are unusable.

- "What's the single most important metric that changed? Can you give me a number?"
- "How does that compare to where you were before — do you have a before/after number?"
- "What's the business impact of that — what does it translate to in dollars, headcount, or time?"
- "Is there a secondary metric that also moved? What was it?"
- "How long did it take to see results?"

**Group 5: Looking Forward (the endorsement)**
> Goal: get a quotable summary and a forward-looking statement.

- "How would you describe what [product] does for your team to a peer who hasn't heard of it?"
- "What would you tell someone who's evaluating [product] right now?"
- "What's next for your team — what are you hoping to do with [product] in the next year?"

### Interview Logistics Tips
- Send questions in advance — customers answer better when they've had time to pull numbers.
- Schedule 30–45 minutes. 20 minutes of good answers beats 60 minutes of vague ones.
- Record with permission. Transcript > notes.
- Ask for the specific number twice: once naturally, once directly ("do you have an exact figure for that?").
- If a result is directional ("we're faster"), probe: "faster by how much? Do you have a before/after time?"

---

## Phase 2: Case Study Draft

### The PSR Structure

Every case study follows Problem → Solution → Results. Every section must earn its place.

**Headline formula:**
`[Client] + [specific result] + with [product]`

Examples:
- "Acme Corp cut cloud costs 43% in 90 days with Sedai"
- "How Techco eliminated manual scaling work and saved 600 engineer-hours per quarter"

Do not use vague headlines: "Acme Corp Sees Improvement with Sedai" is not a headline.

---

**Section 1: Company Context (2–3 sentences)**
- Who the customer is, what they do, their relevant scale
- Why their context matters to the reader (industry, infrastructure complexity, team size)
- Do not oversell the customer — state facts

**Section 2: The Challenge (1–3 paragraphs)**
- Start with the specific problem, not category language
- Name the pain concretely: what was breaking, what was the cost
- Include what they tried before and why it wasn't enough
- End with: "They needed [X] without [unacceptable tradeoff]"

Rules:
- Avoid: "they were struggling with inefficiencies" → use: "their on-call rotation spent 12 hours per week manually adjusting Lambda concurrency"
- Include the business cost of the problem, not just the technical pain
- The customer is the subject of every sentence in this section

**Section 3: Why [Product] (1 paragraph)**
- What made them choose this solution
- What they were skeptical about
- What the deciding factor was
- Keep this short — this is the credibility bridge, not the pitch

Rules:
- Do not make this a product features list
- Include mention of alternatives considered if available

**Section 4: The Solution (1–2 paragraphs)**
- How they deployed and what the implementation looked like
- Who was involved and what the ramp looked like
- What changed about their process or workflow

Rules:
- Customer is still the hero — "the team configured X" not "Sedai automatically does X"
- Be specific about timeline: "within the first two weeks" beats "quickly"
- Include a meaningful quote here if available — something that captures the experience, not the outcome

**Section 5: Results (the most important section)**
Lead with the primary metric. Structure as:
- **Primary result:** [specific number, timeframe, tied to stated problem]
- **Secondary result(s):** [1–2 additional metrics]
- **Business translation:** what those numbers mean in real terms (dollars saved, hours freed, risk reduced)
- **Closing quote:** customer summarizing in their own words — should be something a prospect could read and see themselves in

Rules:
- Every metric must be specific: not "improved" → "43% reduction"; not "faster" → "from 4 hours to 22 minutes"
- Results must tie back to the original stated problem — not standalone metrics
- If you only have one metric, make it count; do not pad with vague language
- Timeframe matters: "in the first 60 days" is more credible than an undated claim

**Section 6: Call to Action (1 sentence)**
- Match to funnel stage
- Options: "See how [product] works → [demo link]" / "Read how [similar company] did it → [link]" / "Talk to our team → [link]"
- Do not include multiple CTAs

---

### Writing Rules

- Customer is the subject of most sentences
- No vendor-hero language: "Sedai enabled them to..." → "The team was able to..."
- No vague adjectives: seamless, powerful, robust, innovative, cutting-edge
- No unsourced statistics (the research killed 15/25 stat claims found online — they are fabricated)
- Short sentences. One idea per sentence.
- Quotes should sound like a human said them, not a press release
- Length: 600–900 words for a standard case study. Long enough to be credible, short enough to be read.

---

## Phase 3: Sales Enablement Tags

Every case study needs metadata so sales reps can retrieve it by situation, not by name.

Produce a sales enablement block for every case study:

```
SALES ENABLEMENT CARD
─────────────────────
Customer:        [name]
Industry:        [vertical]
Company size:    [ARR range or employee count]
Use case:        [specific use case, not product name]
Primary metric:  [number + timeframe]
Positioning proof: [which messaging claim this proves]
Best used when:  [rep situation — e.g., "prospect is mid-market DevOps team worried about implementation complexity"]
Objection match: [the objection this case study answers — e.g., "we don't have the team to manage this"]
Comparable ICP:  [who a rep should send this to — e.g., "fintech companies 200-1000 employees, AWS-heavy"]
Approved quote:  [the best pullable quote, ready to paste into an email]
```

### Proof Library Mapping

When building multiple case studies, map each to the company's core positioning claims. Every claim in your positioning framework should have at least one case study proving it.

Example proof library structure:
| Positioning claim | Proving case study | Confidence |
|---|---|---|
| "No additional headcount required" | Acme Corp | High (CSM-approved quote) |
| "Results in under 60 days" | Techco | Medium (metric is directional) |
| "Works in complex multi-cloud environments" | — | Gap — need this case study |

Flag gaps — missing proof for a positioning claim is a content priority.

---

## Phase 4: Distribution Plan

For each case study, produce a channel-specific distribution plan.

**Website**
- Full case study page (PDF download + HTML version)
- Add to case study library with filterable tags (industry, use case, metric type)
- Add as a "related" link on relevant product pages
- Add a testimonial quote to the homepage or pricing page if the quote is strong enough

**Email**
- Nurture trigger: send when a prospect matches the case study's ICP and has been in pipeline for 14+ days without forward movement
- Subject line formula: "How [Customer] [achieved result] — [1 sentence on relevance to them]"
- Body: 3 sentences max + link. Do not summarize the whole case study in the email.
- Suggested placement: mid-funnel, after demo, before proposal

**LinkedIn**
- Stat post: "[Metric] in [timeframe]. Here's how [Customer] did it." → link to full study
- Quote card: pull the best customer quote, design as image with customer logo
- Behind-the-scenes angle: "The problem [Customer] was actually trying to solve..." (story format, hook-driven)
- Tag the customer contact if they're open to it — their network is more valuable than your followers

**Direct Sales**
- Rep-ready email snippet (2–3 sentences + link) that a rep can paste when sending to a matched prospect
- Deck-ready slide: headline + 2 metrics + quote in one visual
- Objection-matched: note exactly which objection this study answers so reps can deploy at the right moment

**Repurposing (optional, if resource-rich)**
- Blog post: extract the "why they chose us" section into a post about the decision criteria in that industry
- Podcast mention: quote the customer outcome in a relevant episode
- Paid social: top metric as a stat ad with customer logo

---

## Output Format

Produce the output in clearly labeled sections:

```
## PRE-INTERVIEW BRIEF
[Tailored question set, grouped by category]

## CASE STUDY DRAFT
[Headline]
[Full PSR-structured draft]

## SALES ENABLEMENT CARD
[Filled metadata block]

## DISTRIBUTION PLAN
[Channel-by-channel plan]

## PROOF LIBRARY NOTE
[Which positioning claim this proves, any gaps flagged]
```

If the user provides a transcript, skip the pre-interview brief and go straight to the draft.

If the user asks for only one section (e.g., "just write the questions"), produce only that section.

---

## Scaling Case Study Production

When a team needs to produce multiple case studies systematically, recommend this operating model:

**Trigger system:** CSM flags eligible customers at 90-day mark or at renewal. Criteria: customer has a quantified outcome + is willing to be public + fits a gap in the proof library.

**Intake form:** Send customers a 5-question async form before scheduling a call. Ask for: company description, primary metric achieved, timeframe, one quote they'd be comfortable with, and permission level (logo use, quote attribution, full case study).

**Interview → draft SLA:** First draft within 5 business days of interview. Customer review within 10 business days. Publication within 3 days of approval.

**Approval workflow:**
1. Writer sends draft to customer contact
2. Customer edits/approves (1 revision round max)
3. Legal review if required by customer's NDA
4. Internal review (marketing lead sign-off)
5. Publish and distribute

**Cadence target:** 1–2 new case studies per month for a growth-stage SaaS team. Prioritize filling proof library gaps over volume.

**Templates:** Maintain a house template (structure, style guide, sales card format) so any writer can produce a consistent output. This skill is the template.
