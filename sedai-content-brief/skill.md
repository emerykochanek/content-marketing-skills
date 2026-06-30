---
name: sedai-content-brief
description: Generates SEO/GEO/AEO-optimized content briefs for Sedai blog posts and thought leadership. Sits between topic selection and writing. Runs live SERP data, checks keyword clusters, applies messaging guide and VOC, and outputs a full brief with the research behind every decision visible. Use before any content goes to the agency or a writer.
---

# Sedai Content Brief Generator

## What This Skill Does

Takes a topic, target query, or post title and produces a complete content brief ready for a writer or agency. Every structural decision — H1, H2s, word count, sections to include, sections to avoid — is shown with the research source that justifies it.

**The brief is not a guess. Every recommendation cites:**
- SERP data (from live seo-sxo analysis)
- Keyword cluster (volume, KD, cluster role)
- AEO/GEO research foundation rules
- Messaging guide (what Sedai can claim)
- VOC language (Sybill phrases that match this topic)
- Bucket structure requirements

---

## Step 0: Run Before Any Output

Complete in order. Do not skip steps.

0. **Load shared data.** Read `/Users/emkochanek/.claude/skills/sedai-shared/shared-data.md` before doing anything else. This file is the single source of truth for all keyword clusters (9 clusters), VOC language, messaging guide, approved claims, and hard stops. Do not rely on the abbreviated summaries below — the shared file is canonical.

1. **Confirm the target query.** If the user provides a topic or title, extract the single primary query the brief is built around. State it explicitly.

2. **Run seo-sxo** on the primary target query. This is required before producing any H1, H2, or structural recommendation. The SERP Data section of the brief is populated from this output.

3. **Run AI platform monitoring** — query Perplexity, ChatGPT, Gemini, and Claude with the primary target query. Capture what each says, what sources each cites, what language each uses, and what's missing from their answers. Populate the AI Platform Monitoring section of the brief. This determines: what language the brief should mirror, what sources to beat for AI citation, what content gaps the post will fill.

4. **Identify the bucket:**
   - Best-of Listicle
   - Comparison / VS / Alternatives
   - Category Ownership
   - Practitioner Guide
   - Refresh
   - Thought Leadership

5. **Check the keyword cluster.** Identify which cluster this post belongs to and pull the confirmed keywords, volumes, and KD scores. Flag if the target query is in the "do not target" list.

6. **Check sedai.io coverage.** Flag if a page already exists for this query. Never brief a post that duplicates an existing page. Reference: `Sedai_Keyword_Blog_Audit.md` and `sedai.io/sitemap.xml`.

7. **Flag AI Overview targets per H2.** For each H2 in the outline, determine if the implied query would trigger a Google AI Overview. The test: if you'd type the H2 as a question into Google and expect a generative answer box at the top, it's a target. Sections that qualify: definitional ("What is X"), process ("How X works"), comparison ("X vs Y"), requirements ("What X requires"). Sections that don't qualify: persuasion sections ("Why you need X"), use case lists that presuppose the reader already knows the topic, "Who is this for" persona sections. For each qualifying H2: specify the extraction format (paragraph / numbered list / bulleted list / table) based on what the SERP shows Google prefers for that query type.

8. **Validate every H2 as a real query.** After drafting the outline, search each proposed H2 in Perplexity (WebSearch). Confirm it mirrors language people actually use. Replace any H2 that returns no signal or returns a meaningfully different phrasing. Log the confirmed query for each H2 in the brief as the "Research basis." This step is required for all buckets — not just Thought Leadership.

8. **Verify every quantified claim.** Before finalizing the brief, audit the Required Evidence table. For every row marked "needs verification": attempt a direct WebFetch on the named source URL. If the source URL is not known, or if the fetch does not confirm the exact claim, run deep research on that claim using the `deep-research` skill. A claim that cannot be traced to a primary source after deep research must be marked **NEEDS SOURCE** and excluded from the brief. Do not pass unverified stats to a writer.

   **When to invoke deep-research on a claim:**
   - The brief lists a stat but no source URL
   - Direct WebFetch on the named source returns a 403, 404, or doesn't contain the exact claim
   - The stat came from a secondary source (another blog, a vendor recap, an AI-generated summary) and the primary source is unknown
   - The claim is a market projection, industry figure, or third-party benchmark — these are highest-risk for fabrication

   **When NOT to invoke deep-research:**
   - The source URL is already confirmed and the exact claim appears in the fetched page
   - The claim is Sedai internal data (webinar stats, Notes From Suresh, customer proof points) — these are primary sources, cite as-is

**Steps 2 and 3 (seo-sxo + AI platform monitoring) must launch in the same message as parallel tool calls. Do not fetch seo-sxo data first and run AI monitoring second. No output before both return.**

---

## Keyword Clusters (Load Before Every Brief)

### Cluster 1: AI Agent Optimization

| Keyword | Vol | KD | Notes |
|---|---|---|---|
| what is ai agent optimization | low, nascent | low | Sedai owns this term |
| ai agent cost optimization | nascent | low | Core cluster |
| llm cost optimization | 200–500/mo est. | low-moderate | Cast AI competes here |
| how to reduce llm costs | moderate, growing | low | Practitioner Guide target |
| ai agent governance | nascent | low | Secondary |
| finops for ai | 140/mo | KD 21 | |
| ai routing | 210/mo | KD 28 | |
| ai route optimization | 260/mo | KD 24 | |
| claude router | 170/mo | KD 11 | |
| pointfive alternatives | low, spiking | low | 4–6 week window post-Series B |
| aws finops agent alternative | very low, building | low | Time-sensitive |
| retry storms | 0/mo | emerging | Monitor — no content yet |
| tokenomics | watch | — | No content yet |

**Thought leadership cluster:**
- tokenmaxxing
- AI budget crisis 2026
- cost per outcome AI
- why are enterprise AI budgets overrunning
- AI observability for engineering leaders

### Cluster 2: Kubernetes Cost Optimization

**Winning (Sedai already ranks):**
- kubernetes optimization (rank 1, 70/mo)
- kubernetes cost management (rank 5, 70/mo)
- cloud cost optimization best practices (rank 6, 110/mo)
- azure cost management tools (rank 11, 170/mo)
- best cloud cost optimization tools (rank 11, 70/mo)

**Gaps to fill:**
- karpenter vs cluster autoscaler
- kubernetes requests and limits guide
- hpa vs vpa kubernetes (ScaleOps owns — Sedai needs a counter)
- kubernetes bin packing automation (VOC term)
- ec2 right-sizing without incidents (VOC term)

**Do not target:**
- "cloud computing cost savings" (880 vol) — AWS/Gartner/Forbes own this
- "on premises vs cloud" clusters — wrong audience
- Any term where Sedai is currently rank 101+ with no content advantage

---

## Messaging Guide Rules (Apply to Every Brief)

**Claims Sedai is allowed to make — use precisely:**
- "The only platform that optimizes both what your agent runs on and what it calls"
- "Optimize the agents you've already built" — separates Sedai from agent-building platforms
- "One import. Zero rewrites." — state once, not repeatedly
- "Per-agent routers trained on actual production traffic, not generic benchmarks"
- "Sedai acts. Competitors create tickets." — vs PointFive, AWS FinOps Agent

**What NOT to say:**
- "LLM Optimization" as category label — that's Cast AI's term. Use "AI Agent Optimization"
- Position Langfuse, Braintrust, Helicone as competitors — they are complementary
- Claim PointFive "can't optimize" — say they require human review
- Mention GigaOm unless it directly supports a specific claim in that section
- Any stat without a named source

**Competitor framing rules:**
- Describe what each competitor does accurately — use their own website language
- Always include "Where [Competitor] Wins" — pages that acknowledge competitor strengths are cited more often by AI systems
- Never claim Sedai wins on every dimension

---

## VOC Language (Sybill — Apply Where Relevant)

Use these phrases in persona descriptions, section openers, and problem statements:

| Marketing language (avoid) | VOC language (use) |
|---|---|
| "Reduce your cloud costs" | "Eliminate the manual toil of right-sizing" |
| "Optimize Kubernetes" | "Automate bin-packing without the fear of breakage" |
| "Get visibility into your spend" | "Stop alert fatigue and let the system take action" |
| "Automated scaling" | "Handle unpredictable traffic bursts without sacrificing SLOs" |

**High-value VOC phrases to embed:**
- "manual toil" — most common phrase from engineering leads
- "fear of breakage" — core mental barrier, engineers over-provision defensively
- "endless cat-and-mouse game" — right-sizing with developers
- "WTF bills" — finance-triggered urgency
- "visibility but not the power to fix it" — positions against dashboard tools
- "another dashboard to tell me I'm wasting money" — explicit competitor rejection
- "do more with less" — organizational pressure driving urgency
- "set-it-and-forget-it" / "autopilot" — what buyers want
- "bursty" / "wildly unpredictable" — traffic pattern language
- "SLA/SLO wall" — fear that cost-cutting violates performance commitments

---

## Bucket Structure Requirements

### Best-of Listicle

H1 pattern: [Number] Best [Category] Tools for [Use Case] in [Year]
Word count: 2,000–3,500 words total

Required sections in order:
1. Answer capsule (60 words, immediately after H1)
2. H2: How We Evaluated These Tools — explicit criteria required (signals editorial neutrality)
3. H2: Quick Comparison Table — before individual tool entries, not after
4. H2 per tool: [Tool Name] — [One-Line Differentiator]
   - H3: Key Features
   - H3: What It Does Well
   - H3: Limitations (required — builds credibility)
   - H3: Best For
5. H2: How to Choose the Right Tool for Your Stack
6. H2: FAQ (minimum 5 questions, FAQPage schema)

Required elements: Year in H1. Table of contents for 8+ tools. FAQPage schema. Named author with credentials. Visible "Last Updated" date.

### Comparison: VS / Comparison / Alternatives

VS page word count: 1,800–3,000 words
Alternatives page word count: 2,500–4,000 words

VS page required sections:
1. H2: TL;DR — Which Should You Choose? (40–60 words, independently extractable — highest AIO element on comparison pages)
2. H2: Feature Comparison table (8–12 rows, honest caveats)
3. H2: Where [Competitor] Wins
4. H2: Where Sedai Wins
5. H2: [The Core Differentiator] — name the specific technical gap
6. H2: When to Choose [Competitor]
7. H2: When to Choose Sedai
8. H2: FAQ (FAQPage schema)

Alternatives page required sections:
1. H2: Why Teams Look for [Tool] Alternatives — validates search intent
2. H2: Quick Comparison Table
3. H2 per alternative: [Tool] — Best for [Specific Use Case]
4. H2: How to Choose
5. H2: FAQ

### Category Ownership

H1: What is [Term]?
Word count: 1,500–2,500 words

Required sections:
1. H2: What is [Term]? — 1–3 sentences, fully self-contained, independently citable. Most important element on the page. Mirrors the H1 query directly — this is the featured snippet target.
2. H2: How [Term] Works
3. H2: Key Components of [Term]
4. H2: [Term] vs [Adjacent Concept]
5. H2: Who Needs [Term]
6. H2: [Term] Use Cases (3–5 concrete examples)
7. H2: FAQ (FAQPage schema)

### Practitioner Guide: Technical Practitioner Guide

H1 mirrors exact how-to query: "How to [Do X] Without [Risk/Rewrite/Downtime]"
Word count: 2,500–3,500 words

Required sections:
1. Answer capsule after H1
2. H2: Prerequisites — what you need before you can act (structured list, high AIO extraction target)
3. H2: Why [Problem] Is Hard to Solve at Scale
4. H2: Step 1 / Step 2 / Step 3 (numbered — HowTo schema maps to this)
5. H2: Common Mistakes (numbered list — high Perplexity citation target)
6. H2: How to Verify It's Working
7. H2: FAQ

### Thought Leadership

Optimization goal: AI citation and brand authority — not organic rank.
Word count: 800–1,500 words

H1 rules:
- Mirrors the question the reader is already asking
- Under 10 words
- No subtitles — colons only if SERP research confirms the colon format wins for this specific query (default: no colon)
- Test: would a VP Engineering or FinOps lead type this into search?

H2 rules:
- Each must mirror a real query — run in Google and Perplexity before finalizing
- Declarative H2s: make a falsifiable claim ("Why Enterprise AI Budgets Are Overrunning")
- Question H2s: directly answer a practitioner question ("What to Measure Instead of Token Consumption")
- Never narrative chapter titles ("Then the Bill Arrives")

Sedai placement: named once, mid-article, after the problem is established, tied to a specific outcome.

---

## Hard Stops (Apply to All Briefs)

Never recommend these in any brief:
- Colons in H2s — no exceptions
- Colons in H1/titles unless seo-sxo SERP research confirms the colon format wins for that specific query — use sparingly, and never for generic subtitle patterns like "X: Why It Matters" or "X: What It Is and How It Works"
- Em dashes in H1s or H2s
- Subtitles
- Standalone Challenge / Approach / Outcome sections
- Generic CTAs not related to the article topic
- Analogies
- Intro filler ("In today's rapidly evolving landscape...")
- "Visibility" as a Sedai value prop — that's what buyers are leaving behind

---

## Output Format

Every brief produces two documents in sequence:
1. **Detailed Brief** — for Em to review. Contains full research justification, Perplexity validation, SERP data, and sourcing for every recommendation.
2. **Writer Brief** — for the agency/writer. Clean, actionable, no research jargon. Tells the writer what to write and what not to do. No research basis fields, no cluster/bucket terminology.

Do not deliver only one. Both are required on every run.

---

### Document 1: Detailed Brief

```
## Content Brief: [Post Title]

---

### Research Foundation

**Target query:** [primary query]
**Keyword cluster:** [Cluster 1 / Cluster 2 / Thought Leadership]
**Volume:** [Semrush figure or "nascent/emerging"]
**KD:** [score]
**Type:** [Best-of Listicle / Comparison / Category Ownership / Practitioner Guide / Refresh / Thought Leadership]
**Existing Sedai coverage:** [URL if exists / None]
**Time sensitivity:** [flag if time-sensitive — e.g., PointFive Series B window]

---

### SERP Data
[Output from seo-sxo — populate fully, do not summarize]

**Dominant page type:** [type] ([confidence] consensus)
**H1 pattern winning in SERP:** [pattern]
**Content depth norm:** [word count range]
**Schema expectation:** [types]
**Featured snippet format:** [paragraph / numbered list / table]
**Featured snippet language pattern:** [exact text structure AI systems pull for this query — quote actual words/phrases if a snippet exists. The brief's answer capsule and opening H2 must mirror this language.]
**Key competitors ranking:** [list with what each does well and what's missing]

**PAA questions** (from live SERP run — minimum 5, used as H2 candidates and fan-out coverage check):
- [question]
- [question]
- [question]
- [question]
- [question]

**Related searches** (from live SERP run — inform secondary keywords and additional H2 candidates):
- [search]
- [search]
- [search]
- [search]
- [search]

**Competitive structure requirements** (H2 sections present in 3+ top-ranking pages — brief MUST include all of these):
- [section]
- [section]
- [section]

**Critical mismatch (if any):** [Flag if the proposed format does not match what the SERP rewards — be specific about the gap]
**Notable SERP gap Sedai could own:** [Flag any unoccupied angle in the top 10 — competitor weakness, missing topic, emerging term no one has covered]

---

### AI Platform Monitoring
[Run the primary target query in each platform before writing the outline. H2 phrasing, section order, and angle decisions must reflect what these platforms are saying and what they're missing.]

**Perplexity**
- What it says:
- Sources it cites:
- Language it uses (note exact phrases):
- What's missing from its answer:

**ChatGPT**
- What it says:
- Sources it cites:
- Language it uses (note exact phrases):
- What's missing from its answer:

**Gemini**
- What it says:
- Sources it cites:
- Language it uses (note exact phrases):
- What's missing from its answer:

**Claude**
- What it says:
- Sources it cites:
- Language it uses (note exact phrases):
- What's missing from its answer:

**Cross-platform patterns:**
- Language used by 3+ platforms → use in H2s and answer capsule
- Sources cited by 3+ platforms → pages to beat for AI citation
- Gaps in all platform answers → content angles this brief owns

---

### Why This Topic Now
[1–2 sentences tying to keyword cluster data, SERP gap, competitive moment, or VOC signal. Not filler — a specific reason grounded in research.]

---

### Who This Is For
[Specific persona from Sybill VOC — not a job title list. Describe the pain they're in right now, the trigger that sent them searching, and what they need to leave the page with. Use VOC language.]

---

### The Angle
[One sentence on the editorial stance — what makes this different from what already ranks. Not a topic description. A specific point of view. Example: "Most 'Cast AI alternatives' posts list tools with similar dashboards. This one maps four distinct problems — observability, gateway routing, intelligent routing, full-stack governance — and names the right tool for each."]

---

### Winning Outline

**H1:** [recommendation] — *Research basis: [SERP pattern + query it mirrors]*
**URL slug:** /blog/[slug]
**Target word count:** ~[X] words — *Research basis: [competitor average from SERP data]*
**Meta title:** [50–60 characters, primary keyword first]
**Meta description:** [130–150 characters, active voice, ends with CTA]

[Full H2/H3 structure:]

**H2: [heading]** (~[X] words)
*Research basis: [why this section — SERP gap / fan-out sub-query / bucket requirement / AEO rule]*
*Perplexity validation: [exact query searched + what the results confirmed or changed about this H2 phrasing]*
*Format: [paragraph / numbered list / table / definition block]*
*VOC phrase to use: ["[phrase]" from Sybill — appears in section opener or persona description]*
*Keyword: [primary or secondary keyword that belongs here]*
*Featured snippet target: [yes/no — if yes, what format]*
*AI Overview target: [yes/no — if yes: format (paragraph / numbered list / bulleted list / table) + first-sentence rule: must contain a complete standalone answer in 40–60 words before any elaboration. If numbered/bulleted: each item must make sense extracted without surrounding context.]*

[Repeat for each H2]

---

### Required Evidence

For each claim the post needs to make, list the source:

| Claim | Source | URL | Status |
|---|---|---|---|
| [claim] | [named source — Sedai customer data / messaging guide / third-party report] | [URL or "internal"] | [Verified / Needs Deep Research / NEEDS SOURCE] |

**Status definitions:**
- **Verified** — primary source URL confirmed via direct fetch, exact claim present on the page
- **Needs Deep Research** — source is named but unconfirmed, or came from a secondary source; run deep-research before finalizing
- **NEEDS SOURCE** — no source found after deep research; exclude from the brief and flag for engineer input

Do not deliver a brief with any row in "Needs Deep Research" status — resolve all rows to Verified or NEEDS SOURCE before output.

---

### Sedai Proof Points to Use
[Pull from Internal Proof Points doc — only include claims that have a confirmed source]
- [Company] saved [metric] ([source])
- [Product fact] ([messaging guide or product spec])

---

### VOC Phrases to Embed
[List 3–5 Sybill phrases relevant to this topic and where they should appear]
- "[phrase]" → [section where it belongs]

---

### Schema Requirements
- [ ] Article (dateModified required)
- [ ] FAQPage (minimum [X] questions)
- [ ] HowTo (Practitioner Guide only)
- [ ] ItemList (Best-of Listicle only)
- [ ] Product (Comparison VS pages — for each tool compared)

---

### Internal Links
[3–5 specific Sedai pages with anchor text — pulled from sitemap, not invented]
- [URL] — anchor: "[text]"

---

### E-E-A-T Requirements
- [ ] Named author with title and credentials
- [ ] Author LinkedIn linked
- [ ] Publish date + "Last Updated" visible
- [ ] Minimum [X] named primary sources with links
- [ ] At least 1 Sedai customer outcome (company name + specific metric) in body — not product section

---

### Hard Stops for This Post
[Any topic-specific things the writer must not do — pulled from messaging guide, competitor framing rules, or bucket requirements]
- Do not: [specific]
- Do not: [specific]

---

### Agency Notes
[Any context the agency needs that isn't in the structure — competitor behavior, tone guidance, what the reader already knows coming in]
```

---

### Document 2: Writer Brief

```
## Writer Brief: [Post Title]

**For:** [Agency writer name]
**Post type:** [Definitional guide / Listicle / Comparison / Practitioner guide]
**Publish on:** sedai.io/blog

---

### The Assignment
[2–3 sentences. Who is this reader, what problem are they in right now, what do they need to leave the page with. Use VOC language. No jargon.]

**This post is not a product pitch for Sedai.** Sedai appears once, mid-article, tied to a specific outcome.

---

### Post Specs

| | |
|---|---|
| **Title (H1)** | [heading — no em dashes; colon only if SERP research confirmed] |
| **Meta title** | [50–60 chars] |
| **Meta description** | [130–150 chars] |
| **URL slug** | /blog/[slug] |
| **Primary keyword** | [exact match query] |
| **Target audience** | [specific persona — role, company context, what they're evaluating] |
| **Word count** | [range] |

### Keywords

| Keyword | Volume | Role |
|---|---|---|
| [primary keyword] | [vol/mo] | Primary |
| [secondary keyword] | [vol/mo] | Secondary |
| [secondary keyword] | [vol/mo] | Secondary |
| [related keyword] | [vol/mo] | Supporting |

---

### Structure

[For each H2:]

**H2: [heading]**
[Word count]. [What to write — topic, format, specific points to cover, VOC phrase to use if applicable. No research citations. No bucket/cluster language. Just clear instructions.]

---

### AEO/GEO Writing Requirements

These five rules apply to every section. No exceptions.

1. **Passage length:** Write each H2 section as one or more self-contained blocks of 134–167 words. Each block must be readable without context from the sections before or after it. This is the optimal length for AI citation extraction.
2. **First sentence rule:** The first sentence after every H2 must be a direct answer to the question implied by the heading. No throat-clearing ("In this section, we'll explore..."). No restating the heading. Answer first, explain second.
3. **Evidence density:** Include 3–5 specific statistics per 1,000 words. Each stat must name the source inline — not in a footnote or references section at the bottom. "Studies show" is not a source.
4. **Self-contained sections:** A reader should be able to copy any single H2 section and read it cold with no surrounding context. If a section requires the previous section to make sense, it fails this test.
5. **Author and date:** Named author with job title, specific expertise domain, and LinkedIn URL. Visible publish date and "Last Updated" date on the page. Without these, the post is anonymous to AI systems.

---

### Sedai Messaging — Use Exactly as Written
[Pull confirmed claims from messaging guide. List only what applies to this post.]

---

### Do Not Do Any of the Following
[Flat list. Specific. No explanations needed — just clear prohibitions.]

---

### Author
[Named Sedai author requirement — title, LinkedIn, credentials.]
```

---

## Quick Reference: What a Good Brief Produces

Before delivering a brief, confirm:
- [ ] Every H2 was searched in Perplexity and the confirmed query is logged in the "Perplexity validation" field
- [ ] Any H2 with no Perplexity signal was revised or removed
- [ ] H2 phrasing matches the query language people actually use, not editorial labels
- [ ] No H2 contains a colon or em dash — no exceptions
- [ ] H1 colon checked: only present if seo-sxo confirmed the colon format wins for this query
- [ ] No H1 or H2 uses a generic subtitle pattern (e.g. "[Term]: The Short Answer", "[Topic]: What You Need to Know")
- [ ] Category Ownership first H2 is "What is [Term]?" — not a colon variant, not an editorial label

A writer who follows this brief should produce a post that:
- Has an H1 that mirrors the exact target query
- Has an answer capsule in the first 100 words
- Has every H2 opening with a direct answer in the first sentence
- Uses VOC language in at least 2 section openers
- Names Sedai once, mid-article, tied to a specific outcome
- Has a comparison table if it's a VS or listicle format
- Has FAQPage schema with minimum 5 questions
- Cites every stat to a named source
- Acknowledges competitor strengths honestly
