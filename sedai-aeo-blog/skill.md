---
name: sedai-aeo-blog
description: Full content review for Sedai blog posts and thought leadership. Checks against SEO/GEO/AEO research foundation, keyword clusters, messaging guide, VOC language, and bucket structure requirements. Runs live SERP data via seo-sxo before producing any recommendations. Use for drafts, published URLs, or Google Docs.
---

# Sedai Content Review

## What This Skill Does

Reviews any Sedai content — blog post, thought leadership piece, LinkedIn article, or agency draft — against the full research stack: AEO/GEO structure rules, keyword clusters, messaging guide, VOC language, and bucket requirements. Produces a scored checklist, specific rewrites, and a prioritized fix list grounded in sources.

**Core rule:** Read the full content before making any suggestion. Never recommend adding text that the existing content already covers. Every recommendation must cite the research source it comes from.

---

## Step 0: Run Before Anything Else

Before producing any output, complete these steps in order. Do not skip any step.

0. **Load shared data.** Read `/Users/emkochanek/.claude/skills/sedai-shared/shared-data.md` before doing anything else. This file is the single source of truth for all keyword clusters (9 clusters), VOC language, messaging guide, approved claims, competitor framing rules, and hard stops. The abbreviated cluster tables later in this skill are summaries only — the shared file is canonical.

1. **In a single message, launch both of the following in parallel — do not split into separate steps:**
   - **Fetch the full content.** If it is a Google Doc, use the Google Drive MCP tool. If it is a URL, fetch it. If it is pasted text, read it completely.
   - **Launch the seo-sxo agent** on the primary target query. Extract the primary query from the title or focus keyword before fetching — do not wait until after you have read the content to start the agent.

   **These two actions must happen in the same message as parallel tool calls. Never fetch the content first and run seo-sxo second. Never run seo-sxo after reading the content. Splitting them is a critical failure that has happened repeatedly.**

   Wait for both to return before writing a single word of output.

2. **Fetch the brief or outline if one exists.** Ask the user if a brief or content outline was created before this draft. If yes, fetch it and check: does the draft follow the approved structure, angle, and target query from the brief? Flag any deviations before reviewing anything else.

3. **Identify the content type:**
   - Best-of Listicle
   - Comparison / VS / Alternatives
   - Category Ownership
   - Practitioner Guide
   - Refresh
   - Thought Leadership
   - LinkedIn Pulse (Comparison or Thought Leadership distributed on LinkedIn — optimization goal is LLM citation and brand authority, not organic rank. Cannibalization with the source blog is not a concern — LinkedIn articles and blog posts serve different distribution channels.)

4. **Check the keyword cluster.** Identify which cluster this content belongs to (AI Agent Optimization, Kubernetes Cost Optimization, or other) and confirm the primary and secondary keywords from the keyword data in this skill before reviewing structure. Do not infer keyword targets — use only what is listed in the Keyword Clusters section or keyword data the user has uploaded.

5. **Check the SEO KW master files.** The source of truth for all keyword research is:
   `/Users/emkochanek/Desktop/CONTENT MARKETING MASTER - CLAUDE/Marketing Messaging MASTER 2026/SEO KWs/`

   This folder contains:
   - `AI Agent Optimization Content Strategy.pdf` — keyword strategy and content plan for the AI Agent cluster
   - `Sedai __ Pepper - Keyword Analysis Jan'26 - Pages Present (May).pdf` — full keyword audit with rankings, volume, and gap analysis

   Also check for supplementary KW data in Downloads if the user references a recent export:
   - `/Users/emkochanek/Downloads/` — may contain recent gap keyword CSVs and KW tracker exports

   Read the relevant file(s) before assessing keyword coverage or recommending target queries. Never rely on the keyword cluster tables in this skill alone — those are summaries. The PDFs are the source of truth. If a keyword recommendation cannot be validated against these files, say so explicitly rather than proceeding from memory.

---

## Keyword Clusters (Reference Before Every Review)

### Cluster 1: AI Agent Optimization
Primary content: July 2026 AI Agent Optimization Content Plan
Target queries and confirmed keywords:

| Keyword | Vol | KD | Notes |
|---|---|---|---|
| what is ai agent optimization | low, nascent | low | Sedai owns this term — publish definitional page first |
| ai agent cost optimization | nascent | low | Core cluster |
| llm cost optimization | 200–500/mo est. | low-moderate | Cast AI competes here |
| how to reduce llm costs | moderate, growing | low | Practitioner Guide target |
| ai agent governance | nascent | low | Secondary |
| finops for ai | 140/mo | KD 21 | Added June 2026 |
| ai routing | 210/mo | KD 28 | Added June 2026 |
| ai route optimization | 260/mo | KD 24 | Added June 2026 |
| claude router | 170/mo | KD 11 | Added June 2026 |
| pointfive alternatives | low, spiking post-Series B | low | Time-sensitive — 4–6 week window |
| aws finops agent alternative | very low, building | low | Time-sensitive |
| retry storms | 0/mo | emerging | Monitor only — no content yet |
| tokenomics | watch | — | FinOps Foundation adopting — no content yet |

**Thought leadership cluster (tokenmaxxing / AI budget crisis):**
- tokenmaxxing
- AI budget crisis 2026
- cost per outcome AI
- why are enterprise AI budgets overrunning
- AI observability for engineering leaders

### Cluster 2: Kubernetes Cost Optimization
Sedai ranks where topics are specific and technical. Do not target generic "cloud cost" head terms.

**Winning keywords (Sedai already ranks):**
- kubernetes optimization (rank 1, 70/mo)
- kubernetes cost management (rank 5, 70/mo)
- cloud cost optimization best practices (rank 6, 110/mo)
- azure cost management tools (rank 11, 170/mo)

**Gaps to fill:**
- karpenter vs cluster autoscaler
- kubernetes requests and limits guide
- hpa vs vpa kubernetes (ScaleOps owns this — Sedai needs a counter)
- kubernetes bin packing automation (VOC term)
- ec2 right-sizing without incidents (VOC term)

**Do not target:**
- "cloud computing cost savings" (880 vol) — AWS/Gartner/Forbes own this, unwinnable
- "on premises vs cloud" clusters — wrong audience, not Sedai's buyer
- Any term where Sedai is currently rank 101+ with no content advantage

---

## Content Type Requirements

### Thought Leadership (Notes From Suresh, executive LinkedIn articles)

**Optimization goal:** AI citation and brand authority. Not organic search rank.

**Primary citation targets:** ChatGPT, Perplexity, Google AI Overviews for conversational queries.

**Title rules:**
- Mirror the question the reader is already asking — no clever takes, no Twitter-bait phrases
- Under 10 words
- No subtitles
- Colons only if SERP research confirms the colon format wins for this specific query — default to no colon
- Question format or declarative — both work if query-mirroring
- Test: would a platform engineer, FinOps lead, or VP Engineering type this exact phrase into search?

**H2 rules for thought leadership:**
- Each H2 must mirror a real query the audience would type
- Run the query in Google and Perplexity before finalizing — check what's in the AI Overview and People Also Ask
- Declarative H2s work when they make a falsifiable claim ("Why Enterprise AI Budgets Are Overrunning")
- Question H2s work when the section directly answers a practitioner question ("What to Measure Instead of Token Consumption")
- Never use narrative H2s that only work as chapter titles in a read-through ("Then the Bill Arrives" — does not function as a standalone citation anchor)

**Sedai placement in thought leadership:**
- Named once, mid-article, after the problem is established
- Must be tied to a specific action or outcome ("We turned on agent observability and found a third of our LLM costs were optimizable")
- Never in the first two paragraphs
- Never as the conclusion

**Evidence rules:**
- Every major claim needs a named source with a link (Goldman Sachs, Gartner, KPMG — not "studies show")
- Statistics with specific numbers: +62% citation influence vs. unattributed claims
- Sedai customer outcomes must include company name + specific metric when used

### Best-of Listicle

H1 pattern: [Number] Best [Category] Tools for [Use Case] in [Year]

Default sections — verify against the SERP run before applying. If ranking pages don't use one of these sections, flag it rather than requiring it blindly:
1. H2: How We Evaluated These Tools (signals editorial neutrality — check if top-ranking pages use this)
2. H2: Quick Comparison Table (before individual entries — most AI-extractable element)
3. H2 per tool: [Tool Name] — one-line differentiator grounded in how that tool is described in its own docs or SERP snippets, not invented
4. H2: How to Choose the Right Tool for Your Stack (verify PAA/related searches support this angle)
5. H2: FAQ (minimum 5 questions — questions must come from PAA, not generated)

Honest competitor treatment is required. AI systems do not cite "we win everything" pages.

### Comparison / VS / Alternatives

VS page H1: [Tool A] vs [Tool B] — [Differentiating Frame]
Alternatives page H1: [Number] Best [Tool] Alternatives in [Year] for [Use Case]

Default sections — verify against the SERP run before applying:
- H2: TL;DR — Which Should You Choose? (40–60 words, independently extractable — verify this appears in ranking comparison pages)
- H2: Feature Comparison table (8–12 rows, honest caveats including where competitors are stronger — this is where competitor strengths live, not in a dedicated section)
- H2: When to Choose [Tool A] / When to Choose [Tool B] (verify SERP rewards this framing)

**Note on "Where [Competitor] Wins":** Acknowledging competitor strengths is required for GEO credibility, but on Sedai's own blog, a standalone H2 that elevates a direct competitor by name is not appropriate. Handle competitor strengths honestly inside the comparison table and within each tool's per-entry section — never as a dedicated top-level heading that promotes the competitor.

### Category Ownership

H1: What is [Term]?
Most important element: Short Answer H2 immediately after H1 — 1–3 sentences, fully self-contained, no surrounding context required.

### Practitioner Guide: Technical Practitioner Guide

H1 mirrors the exact how-to query: "How to [Do X] Without [Risk/Rewrite/Downtime]"
Step-by-step structure required. HowTo schema. Numbered mistakes section (high Perplexity citation target).

---

## The 7 AEO Checkpoints

### Checkpoint 1: Structural Elements

Check for presence and quality:

**Answer Capsule** — 50–80 words immediately after H1. Follows "X is..." or "X refers to..." pattern. Self-contained without surrounding context. Highest-probability passage for Google AIO and Perplexity citation.

**TL;DR / Key Takeaways** — Before first H2 on posts over 1,000 words. 3–5 bullets, each a standalone factual claim (not "we'll cover X").

**Table of Contents** — Required for posts over 1,000 words. H2-level only.

**Summary Table** — 4–8 row Q&A or comparison table. Questions must match search queries. Answers 1–2 sentences only.

Scoring: All 4 present and well-formed ✅ | Missing 1–2 ⚠️ | Missing 3+ ❌

---

### Checkpoint 2: Section Extractability

Test every H2:
1. Does the opening sentence directly answer the question implied by the heading?
2. Can this section be read in isolation and still be a complete answer?
3. Is there a specific claim, fact, or definition in the first two sentences?

**Strong opening:**
> [H2: How Do You Right-Size EC2 Without Breaking Production?]
> "Safe EC2 right-sizing requires classifying workloads by function, validating changes in staging under realistic load, and maintaining a rollback path for production."

**Weak opening (rewrite this):**
> "Right-sizing is one of the most impactful things you can do to reduce AWS costs. In this section, we'll walk through how to approach it safely."

For every weak opening: rewrite first 2 sentences to lead with the direct answer. Show before/after.

---

### Checkpoint 2b: H2 SEO/AEO/GEO Query Optimization

Every H2 is evaluated against three signals. Run this check on every H2 before outputting any recommendations.

**Three-signal test for each H2:**
1. **Query match** — Would a human type this exact phrase (or a close variant) into Google or an AI system? Test by checking if it mirrors a PAA question, related search, or ranking H2 from the SERP run. If no real query supports the framing, it fails.
2. **Snippet/PAA extraction potential** — Question H2s ("How does X work?", "What are the limitations of Y?", "Is X safe for Z?") are the highest-probability extraction format for Google AIO and Perplexity. "Where does X fall short" is weaker than "What are the limitations of X." "What does X look like" is weaker than "How does X work." "Why X should do Y" is weaker than "Is X safe for Y?"
3. **Competitive signal** — How does this H2 framing compare to the H2s ranking in the top competitor pages found in the SERP run? If a competitor owns a stronger framing for the same sub-topic, this H2 needs to match or beat it.

**Common H2 failure patterns:**
- **Product-named H2s** ("How Sedai Rightsizes Kubernetes Pods") — nobody searches a brand name in a how-to. Rewrite to the generic how-to query ("How to Rightsize Kubernetes Pods Without Restarting Them") and let Sedai be the named example inside the section.
- **Editorial conclusion H2s** ("Why Pod Rightsizing Should Run Itself, Not Restart Itself") — works as a chapter title in a read-through, but does not function as a standalone citation anchor. Rewrite to the practitioner question it answers ("Is Autonomous Kubernetes Pod Rightsizing Safe for Production?").
- **"Where does X fall short" / "What does X look like"** — weak question framing. "What are the limitations of X" and "How does X work" are higher-probability extraction formats.
- **Decorative H2s with no query signal** ("What Teams Gain From Autonomous Rightsizing") — generic benefit labels that no one searches. Either rewrite to a data-anchored query ("How Much Can Kubernetes Pod Rightsizing Save?") or fold the content into an adjacent section.
- **Title-format H2s** ("A Practical Checklist for Kubernetes Pod Rightsizing") — the "A Practical..." opener signals editorial voice, not query mirroring. Strip to the query ("Kubernetes Pod Rightsizing Checklist").

**Output format for this checkpoint:**

Every H2 in the article must appear in this table. There are no automatic "Keep" H2s — every heading goes through the three-signal test before a verdict is assigned. "Keep" means it passed all three signals, not that it was skipped.

| H2 | Query match | Snippet potential | Action |
|---|---|---|---|
| [exact H2 text] | ✅ / ⚠️ / ❌ | ✅ / ⚠️ / ❌ | Keep / Fix opening sentence / **Rewrite** |

For every H2 marked **Rewrite**, output:
- Recommended replacement — mirrors query: [exact query it mirrors], source: [PAA / related search / ranking H2 from SERP run / keyword cluster entry]
- No colons, no em dashes in any recommended H2.

Do not recommend a rewrite unless a real query source from the SERP run supports the replacement framing.

---

### Checkpoint 3: Query Fan-Out Coverage

AI systems generate 2–3 sub-queries per topic (88.6% generate exactly 2, per AirOps research on 16,851 queries).

Fan-out sub-queries must come from real data sources — never generate them from intuition:
- **PAA questions** pulled from the seo-sxo SERP run for this article's primary query
- **Related searches** from the same SERP run
- **Keyword cluster entries** in this skill that are topically adjacent to the primary query
- **Ranking H2s** found in top competitor pages during the SERP run

1. List the PAA questions and related searches captured from the SERP run
2. Map each to a section in the article — covered or not covered
3. Flag gaps with the source: "This post has no coverage for [sub-query from PAA/related search]. AI systems will cite a competitor instead."
4. Do not flag a sub-query gap unless it came from one of the four sources above

---

### Checkpoint 4: E-E-A-T Signals

| Signal | Strong | Fix |
|---|---|---|
| Author byline | Named author with title + credentials | Add name, title, domain expertise |
| Publication date | Visible on page | Add publish date + "Last updated: [date]" |
| Primary sources | Named studies/reports with links | Replace "studies show" with named source |
| Customer proof | Named company + specific metric relevant to article topic | Never "customers save money"; only flag missing if a relevant proof point exists or would directly fit |
| Author credentials link | LinkedIn or bio page linked | Add sameAs link |
| Content freshness | Updated within 90 days | Flag if stale — 3.5x citation drop after 6 months |

Minimum bar: author name + date + 2 named primary sources. Without these, the post is anonymous to AI systems.

---

### Checkpoint 5: Per-Provider Optimization

| Provider | Primary Signal | What to Check |
|---|---|---|
| Google AI Overviews | Organic top-10 rank | Answer Capsule and Summary Table present? |
| ChatGPT | Freshness + structure | Publish date visible? Clean H1→H2→H3 hierarchy? |
| Perplexity | Niche specificity | Is this post focused on a specific sub-topic? Check the top 2–3 ranking pages from the SERP run — does this post cover the topic at greater depth or specificity than what is already ranking? Do not assess depth from intuition. |
| Gemini | Authority + structure | Named author with credentials? Article/FAQPage schema? |
| Claude | Source attribution | Claims attributed to named sources? Customer outcomes cite company + metric? |

For each provider where the post is weak: output 1 specific fix.

---

### Checkpoint 6: Keyword and VOC Alignment

Check that the content uses the language Sedai's buyers actually use (from Voice_of_Customer_Sybill.md):

**VOC phrases to look for (use these, not marketing language):**
- "manual toil" — not "reduce manual work"
- "fear of breakage" — not "safe optimization"
- "endless cat-and-mouse game" — not "ongoing tuning challenges"
- "WTF bills" — for finance-triggered content
- "garbage recommendations" — when describing competitor tools
- "visibility but not the power to fix it" — for competitor contrast
- "another dashboard to tell me I'm wasting money" — for positioning against legacy tools
- "do more with less" — the organizational pressure driving urgency
- "set-it-and-forget-it" / "autopilot" — what buyers want
- "bursty" / "wildly unpredictable" — traffic pattern language
- "SLA/SLO wall" — the fear that cost-cutting violates performance commitments

**Check:** Does the content use any of these phrases or their equivalents? If not, flag which sections could incorporate them — but only flag a placement if the section topic directly matches the VOC phrase's documented context (e.g., "SLA/SLO wall" belongs in a section about cost-cutting risk, not in an intro). Do not suggest VOC placement based on feel.

**Keyword check:** Does the primary H1 and at least 2 H2s mirror the target query from the relevant cluster? If the post is in the AI Agent Optimization cluster, check against Cluster 1 keywords. If Kubernetes, check against Cluster 2.

---

### Checkpoint 7: Original Research and Data Gaps

AI systems weight unique data points highly. Check:

1. Does the post cite third-party statistics? → Flag whether a Sedai-native data point could replace or augment it
2. Are there claims without supporting data? → Flag as "original research opportunity"
3. Are Sedai customer outcomes buried in a product section? → Move into the body as evidence for an educational claim

**Sedai's citability assets (use in body, not product sections):**
- 25M+ autonomous actions executed in production
- $3.5M saved at Palo Alto Networks (89,000+ changes, zero incidents)
- 27% AWS cost reduction at KnowBe4 ($1.2M saved)
- A third of LLM costs optimizable after turning on agent observability (from Notes From Suresh)

**Customer proof relevance rule:** Only recommend adding a customer proof point when it directly proves an educational claim the article already makes — not to satisfy a template or add credibility in the abstract. The test: could you remove the proof point and the article's argument still holds? If yes, the proof point is decorative and should not be added. If the proof point is the evidence for a specific claim ("application-aware optimization avoids SLO breaches"), then it belongs in the body adjacent to that claim — not in a standalone product section.

Do not suggest adding a Kubernetes customer outcome to an AI agent article, or a Lambda outcome to an EKS article. For multi-service articles (e.g. Lambda vs ECS vs EKS), the proof point must be specific to one of the services being compared — a general "AWS optimization" outcome does not qualify. If the only available proof point is generic, flag the gap rather than using it. If no directly relevant proof point exists, flag it as a gap ("No customer proof point exists for this specific use case — candidate for future case study") rather than recommending a tangential one.

Never recommend inserting a customer quote at the end of a product section as a default pattern. That is template stuffing, not evidence-based writing.

Flag any unsourced claim as: "Original research opportunity: [claim]. What does Sedai's platform data show here?"

---

### Checkpoint 8: Product Integration Quality

Product should appear as the natural answer to a gap the reader has already felt.

The correct pattern:
1. Teach the right approach (neutral, educational)
2. Surface the gap: "this is why most teams can't execute this manually at scale"
3. Customer outcome as proof (named company, specific metric)
4. Sedai as the example of what solving it looks like

**Red flags — fix these:**
- Sedai appearing in the second paragraph → too early, earn it
- "Sedai is an autonomous cloud optimization platform that..." → feature-first, rewrite to outcome-first
- Standalone "Book a demo" without a customer outcome before it
- "How it works" section that only describes Sedai → must describe how the category works, with Sedai as one named example

**Green flags — keep/add:**
- "[Company] saved [specific outcome] using [approach Sedai enables]" before naming Sedai
- "This is why teams at [Company] moved from manual tuning to..." — outcome-first bridge
- Customer quotes with name, title, and company

---

## Messaging Guide Rules (Apply to All Content)

From AI Agent Optimization Messaging Guide (Rich Bentley, May 2026):

**Claims Sedai is allowed to make (use precisely, not loosely):**
- "The only platform that optimizes both what your agent runs on and what it calls" — full-stack differentiator
- "Optimize the agents you've already built" — scope qualifier that separates Sedai from agent-building platforms (CrewAI, LangChain, AutoGen)
- "One import. Zero rewrites." — developer value prop; state once, not repeatedly
- "Per-agent routers trained on actual production traffic, not generic benchmarks" — differentiator vs PortKey, LiteLLM
- "Sedai acts. Competitors create tickets." — differentiator vs PointFive, AWS FinOps Agent

**What NOT to say:**
- "LLM Optimization" as the category label — that's Cast AI's term. Use "AI Agent Optimization"
- Position Langfuse, Braintrust, or Helicone as competitors — they are complementary; Sedai integrates with them
- Claim PointFive "can't optimize" — say they require human review (that's what their own website says)
- Mention GigaOm unless it directly supports a specific claim in that section
- Any stat without a named source

---

## Hard Stops (Applies to All Content)

These should never appear in any Sedai content:

- Colons in H2s — no exceptions
- Colons in titles/H1s — allowed only if seo-sxo SERP research confirms the colon format wins for that specific query. Use sparingly. "X: Why It Matters," "X: What It Is and How It Works," and other generic subtitle patterns are never acceptable regardless of SERP data — research must confirm the specific colon framing, not just colons generally
- Em dashes in titles, H1s, or H2s
- Subtitles separated by colons or em dashes
- 1–2 sentence paragraph rule (paragraphs can be 3–4 sentences)
- Standalone Challenge / Approach / Outcome sections
- Generic CTAs not related to the article topic
- Vague or empty analogies — the kind LLMs generate as filler ("like a conductor orchestrating a symphony," "think of it as a traffic cop for your cloud"). Concrete, technically grounded illustrations that recur through a piece and do real explanatory work are acceptable. Test: does the illustration add technical clarity that a direct statement would lose? If yes, keep it. If it could be removed and replaced with a direct claim without losing meaning, it is filler.
- Intro filler ("In today's rapidly evolving landscape...")
- "Visibility" as a value prop — that's what buyers are leaving behind

---

## Output Format

Every review produces two documents in sequence. Do not deliver only one — both are required on every run.

1. **Full Review** — for Em. Contains all checkpoint scores, SERP data, sourced findings, and research justification.
2. **Agency Review** — for the agency. One-page brief. Numbered actions, before/after rewrites, checklist. No research jargon, no checkpoint numbers, no source citations.

---

### Document 1: Full Review

```
## Content Review: [Post Title or Doc Name]
**Type:** [Best-of Listicle / Comparison / Category Ownership / Practitioner Guide / Refresh / Thought Leadership]
**Primary target query:** [query]
**Keyword cluster:** [AI Agent Optimization / Kubernetes / Other]
**Date reviewed:** [date]
**Overall score:** [XX/100]

---

### SERP Data (from seo-sxo)
[What the SERP shows for the primary query — page type winning, H2 patterns in top results, featured snippet language]

---

### Checkpoint Scores
| Checkpoint | Score | Status |
|---|---|---|
| 1. Structural Elements | /15 | ✅ / ⚠️ / ❌ |
| 2. Section Extractability | /15 | |
| 2b. H2 Query Optimization | /10 | |
| 3. Query Fan-Out Coverage | /15 | |
| 4. E-E-A-T Signals | /15 | |
| 5. Per-Provider Optimization | /10 | |
| 6. Keyword and VOC Alignment | /15 | |
| 7. Original Research Gaps | /10 | |
| 8. Product Integration | /5 | |
| **Total** | **/100** | |

---

### Priority Fixes (in order of impact)
1. [Fix] — [source: research foundation / keyword cluster / messaging guide / VOC]
2. ...

---

### H2 Query Optimization
[Run for every H2 in the article.]

| H2 | Query match | Snippet potential | Action |
|---|---|---|---|
| [H2 text] | ✅/⚠️/❌ | ✅/⚠️/❌ | Keep / Fix opening / **Rewrite** |

For every **Rewrite**:
- **[H2 text]:** Recommended → "[new H2]" — mirrors query: [query], source: [PAA / related search / ranking H2 / keyword cluster]

---

### Title and H2 Recommendations
[Only output after SERP data is reviewed. Each recommendation cites the query it mirrors and the SERP signal that supports it.]

**Title rule:** The goal is to recommend a title grounded in SERP length patterns, that mirrors the primary KW or LLM query, and is short enough to rank and be cited. A colon in the existing title is often a symptom of an overly long or structured title — but if SERP research shows the colon format is what wins for this specific query, keeping it (or recommending a colon title) is the right call. The fix is a researched replacement, not a punctuation edit in either direction.

Before recommending any H1:
1. List the actual titles of the top 3–5 ranking pages for the primary query from the SERP run
2. Note the length pattern (word count range, structure — keyword-first vs. question vs. declarative)
3. Check the primary keyword from the KW cluster — it must appear in the title
4. Check LLM query phrasing — would ChatGPT or Perplexity surface this title as an answer to a conversational query? If not, adjust phrasing toward how the question is actually asked
5. Recommend a title that fits the length pattern, leads with the KW, and would surface naturally in an AI answer — not just the existing title with a colon swapped for an em dash

Never recommend just removing the colon and leaving the rest unchanged. Always recommend a fully researched replacement.

Note: the title tag (meta title, shown in SERP) and the H1 (on-page heading) are different. The title tag must stay under 60 characters. The H1 can be slightly longer but must still follow the SERP length pattern.

**H1:** [recommendation] — mirrors query: [query], supported by: [SERP signal], matches length pattern of: [example ranking title], KW present: [yes/no]

**H2 recommendations must be grounded in real queries.** For every H2 suggestion:
1. State the search query it mirrors (e.g., "karpenter vs cast ai", "is cast ai safe for production")
2. Cite the signal that supports it — PAA question, related search, ranking H2 found in SERP, or keyword cluster entry
3. Never generate H2 labels from intuition or descriptive logic alone ("Pod-Level Rightsizing for Teams Already on Karpenter" is a label, not a query — do not recommend it unless a real search query supports it)

For per-tool H2s on Comparison pages: run a search for "[tool name] review", "[tool name] vs cast ai", and "[tool name] kubernetes" to find the language searchers actually use before writing the differentiator label.

**H2 [section name]:** [recommendation] — mirrors query: [query], source: [PAA / related search / keyword cluster / ranking H2]

---

### Missing Sections — H2s and H3s to Add

For every PAA question, related search, or ranking H2 pattern from the SERP run that is not covered by an existing section, recommend adding a new H2 or H3. Do not only flag what is broken — flag what is missing entirely.

Format:

**Add H2: [recommended heading]**
Why: [PAA question / related search / ranking H2 pattern it addresses — cite the source]
Where: [after which existing section it should appear]
Format: [paragraph / numbered list / table / definition block]
Word count: [~X words]

**Add H3 under [parent H2]: [recommended heading]**
Why: [source]
Format: [format]

If the post is missing a section that every top-ranking competitor has (e.g., cost comparison, tooling comparison, migration paths), flag it as a **competitive gap** — not just a fan-out gap. These are the sections most likely to determine whether the post ranks or gets cited.

---

### Specific Rewrites

**[Section name] — Extractability fix:**
Before: "[original first 2 sentences]"
After: "[rewritten opening that leads with the direct answer]"
Source: [cite the actual source — AEO extractability rule / VOC phrase / messaging guide claim / keyword from cluster / SERP signal — never cite a made-up section number]

**[Section name] — VOC fix:**
Before: "[original language]"
After: "[rewritten using VOC phrase from the VOC list in this skill — only use phrases that appear in that list, do not invent VOC-sounding language]"
Source: VOC phrase: "[exact phrase]" from Voice_of_Customer_Sybill.md

**Rewrite quality check — before outputting any rewrite:**
- Does the "After" version use language from the VOC list, keyword cluster, or messaging guide? If not, revise until it does.
- Does the "After" version contain any claim not present in the original draft or in the research sources? If yes, remove it — do not add new claims.
- Does the "After" version inadvertently use a phrase from the "What NOT to say" list in the Messaging Guide? If yes, rewrite.

---

### Fan-Out Gap Analysis
Primary query: [query]
Source of sub-queries: [list which PAA questions and related searches were pulled from the SERP run]

Sub-query A: [sub-query] — source: [PAA / related search / keyword cluster entry] → [covered / not covered]
Sub-query B: [sub-query] — source: [PAA / related search / keyword cluster entry] → [covered / not covered]

Recommendation: [what to add — cite the specific PAA question or related search that creates the gap. Do not recommend additions that aren't grounded in a real search signal.]

---

### Keyword and VOC Gaps
- H1 uses target keyword: [yes/no]
- VOC phrases present: [list which ones found]
- VOC phrases missing that fit this content: [list with suggested placement]
- Keyword cluster alignment: [aligned / misaligned — explain]

---

### E-E-A-T Missing Elements
- [ ] Author byline with credentials
- [ ] Publication date
- [ ] Named primary sources
- [ ] Customer outcome with company name + metric
```

---

### Document 2: Agency Review

```
## Agency Review: [Post Title]
**Post type:** [Practitioner Guide / Comparison / Listicle / Thought Leadership]
**Reviewed:** [date]

---

### Must Fix Before Publishing

[List only true hard stops — structural violations that will harm SEO or violate Sedai content rules. No more than 5. One line each. No explanation — just the problem and the fix.]

1. **[Issue]** — [one-line fix]
2. ...

---

### Priority Edits (in order)

[Numbered list. Each item is one thing to do. No research context, no checkpoint references, no "source: X." Just what to change and how. Include any before/after examples inline.]

1. **[What to fix]**
   [One sentence on how to fix it. If a rewrite is needed, show it here.]

2. **[What to fix]**
   [One sentence on how to fix it.]

[Continue for all priority fixes — typically 5–8 items]

---

### H2 Changes

[Table format. Show every H2 that needs a change. "Keep" H2s are omitted — only show what needs action.]

| Current H2 | Change | New H2 (if rewrite needed) |
|---|---|---|
| [H2 text] | Fix opening sentence | — |
| [H2 text] | Rewrite | [new H2] |

---

### Sections to Add

[List every H2 or H3 that needs to be added — missing coverage from PAA, competitive gap vs. ranking pages, or fan-out sub-query with no existing section. Show where it goes and what it should cover.]

**Add H2: [heading]**
Goes after: [existing section]
Cover: [what to write — specific, no jargon]

---

### Opening Sentence Fixes

[For every H2 marked "fix opening sentence" above, show the before and after. Only the first 1–2 sentences. No explanation.]

**[Section name]**
Before: "[original]"
After: "[rewrite]"

---

### Before You Publish — Checklist

- [ ] Title colon checked against SERP research — if no research confirms colon format wins, remove it
- [ ] Author name and credentials added
- [ ] Publish date added
- [ ] [Any post-specific item flagged in this review]
- [ ] [Any post-specific item flagged in this review]
```

---

## Quick Reference: What Good Looks Like

A post that wins AI citations has:
- H1 that mirrors the exact target query
- Answer Capsule in the first 100 words ("X is...") — self-contained, no surrounding context needed
- Every H2 opening with a direct answer in the first sentence
- Summary Table with 4+ Q&A rows matching search queries
- Author name, title, and date visible on page
- At least 2 named primary sources with links
- At least 1 Sedai customer outcome (company name + specific metric) in the body, not the product section
- Sedai mentioned after a problem is established, not before
- VOC language from Sybill in section openers and persona descriptions
- Fan-out sub-queries covered by dedicated H2 sections or linked companion pages
- FAQPage schema with minimum 5 questions
- No H2 colons, no analogies, no intro filler — title colons only if SERP research confirms
