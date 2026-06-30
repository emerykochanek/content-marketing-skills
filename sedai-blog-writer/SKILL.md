---
name: sedai-blog-writer
description: Write a fully drafted, publish-ready Sedai blog post from a completed content brief. Use this skill whenever the user has a content brief and wants to produce a draft — whether they say "write the blog post," "draft this," "turn this brief into a post," or "write this up." Also use when the user pastes a brief and asks for a draft, or when they're moving from the brief stage (sedai-content-brief) to the writing stage. Always use this skill before producing any long-form blog content for Sedai — do not write directly from a brief without invoking it.
---

# Sedai Blog Writer

Produce a fully drafted, publish-ready Sedai blog post from a completed content brief. This skill has one non-negotiable rule: **every metric, statistic, and quantified claim must be verified against a primary source before it appears in the draft.** If a claim cannot be sourced, it is flagged for engineer input or removed.

---

## Step 0: Load Before Writing

Before producing any output, complete these steps in order:

1. **Read the shared data file:**
   `/Users/emkochanek/.claude/skills/sedai-shared/shared-data.md`
   This is the source of truth for keyword clusters, VOC language, messaging, approved claims, competitor framing rules, and hard stops.

2. **Run seo-sxo in parallel with reading the brief.** Launch the seo-sxo agent on the primary target query at the same time as you read the brief — do not wait until after. Both must return before you write a single word of the draft.

3. **Run a fresh AI platform check.** At write time — not at brief time — check what ChatGPT, Perplexity, and Gemini are currently returning for the primary query. The brief's AI Platform Monitoring section is a snapshot from an earlier session and may have drifted. This step is non-negotiable for any post targeting GEO/AEO. Do this in parallel with seo-sxo and the brief read.

   For each platform, record: (a) how they define the primary term, (b) what language they use, (c) what the top follow-up questions are.

   Before writing the definition section (the first H2), compare what the platforms return against the brief's proposed definition. If they diverge:
   - The post must open with the definition the platforms agree on, then introduce Sedai's category framing as the next layer
   - Do not open with Sedai's definition if it contradicts what users are already being told by AI systems — that mismatch kills AEO citability
   - Flag the divergence explicitly so the writer can decide whether to update the brief

4. **Run deep research on the core technical concepts.** For every technical mechanism the post describes — routing, observability, governance, retry logic, fallback behavior, cost attribution, or whatever the brief covers — run `/deep-research` to verify that the descriptions are technically accurate and not just plausible-sounding. This is separate from claim sourcing. A sourced stat can sit inside a technically wrong explanation.

   Specifically: for each technical section in the brief, ask deep research to find how practitioners actually implement this, what the real failure modes are, and what the technical literature or engineering blogs say. Then compare against what the brief says. If the brief's description is shallow or inaccurate, rewrite the section before drafting.

   This step surfaces content that makes the post genuinely useful to an engineer — not just correct on numbers, but correct on mechanisms. A post that only an engineer could write (or that an engineer would find worth reading) is the target.

   Flag anything the brief oversimplifies or gets wrong. Do not reproduce the brief's framing if deep research shows it is inaccurate.

5. **Read the brief completely.** Extract every claim, stat, and metric the brief asks you to include. List them before proceeding to Step 1.

---

## Step 1: Source Every Claim

This is the most important step. The failure mode this skill exists to prevent: including statistics from secondary sources (blogs, summaries, research agents) without tracing them to a named primary source.

For every claim, metric, or statistic in the brief:

- **Fetch the primary source directly.** Use WebFetch on the actual source URL — not a summary of it. If the brief lists "Goldman Sachs via FinOps X 2026," fetch the FinOps X recap page and confirm the stat is there with that attribution.
- **Verify the exact number.** Numbers change between secondary and primary sources. Use what the primary source says, not what the brief says if they differ.
- **Record source URL and exact quote** for each verified claim before writing.

If a claim cannot be verified via direct WebFetch:
1. **Run deep research first** — invoke the `deep-research` skill on the specific claim before giving up. Many primary sources exist but aren't linked from secondary sources. Deep research finds them.
2. If deep research returns a verified primary source, add it to the sourcing table and proceed.
3. If deep research cannot find a primary source after a full search, flag the claim as **[NEEDS SOURCE]** in the sourcing table, do not include it in the draft, and note it needs engineer input or removal.

**When deep research is required (not optional):**
- Any market projection or industry statistic where the named source is a secondary blog or vendor recap
- Any claim in the Use Cases section that references a specific company, outcome, or number — real documented examples only; if none surface from deep research, write the scenario without specific figures and frame it explicitly as a representative pattern
- Any benchmark figure (e.g., cache hit rates, token overhead per tool, cost multipliers) where the methodology is not described on the source page

**Sedai internal data** (webinar stats, Notes From Suresh, customer proof points) — these are primary sources. Use them as-is with attribution to the Sedai source.

**Secondary source rule:** A secondary source (another blog, a research summary, a vendor's recap) is not a citation. It is a pointer to a primary source. Follow the pointer. If the pointer leads nowhere, the claim does not go in the draft.

**Known verified sources for AI tokenomics posts (use these directly):**
- Goldman Sachs 24x / 120 quadrillion token projection: https://www.goldmansachs.com/insights/articles/ai-agents-forecast-to-boost-tech-cash-flow-as-usage-soars (403 to bots — attribute as "Goldman Sachs Research, Jim Schneider" with URL)
- 30x–200x cost variance: https://www.finops.org/wg/how-to-forecast-ai-services-costs-in-cloud/ (exact quote: "30x to 200X cost delta from the most expensive leading vendor base user with no optimizations...")
- Claude prompt caching (90% off reads): https://platform.claude.com/docs/en/docs/build-with-claude/prompt-caching
- Extended thinking billed at output rate: https://platform.claude.com/docs/en/docs/build-with-claude/extended-thinking
- Tool definition token overhead: describe the mechanism (each tool definition serialized and sent as input on every request) — no verified per-tool figure exists; ask eng team for production data
- Cache hit rates in production (60–85%): https://projectdiscovery.io/blog/how-we-cut-llm-cost-with-prompt-caching
- FinOps operational levers (routing, prompts, caching, attribution): https://www.finops.org/wg/optimizing-genai-usage/
- Runaway cost guardrails: https://www.finops.org/wg/finops-for-ai-overview/
- Tokenomics Foundation (Linux Foundation): https://tokeneconomics.com

**Known unverifiable claims — never include without engineer input:**
- Specific turn-by-turn context cost multipliers (e.g. "7x at turn 10") — no primary source exists; use "agent costs run 3–10x higher than single-turn completions due to context accumulation" only if sourced
- Model allow/deny lists — not a FinOps Foundation concept; reframe as a platform-level governance control if used
- GPT-4o and Gemini 2.0 Flash — both deprecated as of June 2026; use current model names only

---

## Step 2: Write the Draft

With verified claims in hand, write the post following the brief's outline exactly. Apply these rules throughout:

### Structure
- Follow the H1, H2, H3 structure in the brief exactly — do not reorder or rename sections
- Each H2 section must be self-contained: a reader should understand it without reading surrounding sections
- First sentence after every H2 must directly answer the question implied by the heading — no throat-clearing
- Evidence density: 3–5 verified stats per 1,000 words

### Voice
Pattern from Suresh Mathew's published posts at sedai.io/blog — direct, evidence-led, no filler. The reader is an engineering leader or FinOps practitioner. Write at that level.

- **Say the actual thing.** After writing any sentence, ask: what does this mean in plain terms? If the answer is a different, clearer sentence — write that one instead. Do not compress meaning into abstract phrases that sound like they mean something but require the reader to infer the substance. "No attribution layer that explains why" means nothing. "They can't tell which agent or team caused the cost spike" means something. Write the second version.
- State the point, then support it with evidence
- No analogies ("think of tokens like...", "just like a highway toll...")
- No intro filler ("In today's AI landscape...", "As AI continues to...")
- Short paragraphs — 3–4 sentences max
- **Transitions are required between every paragraph and between sentences that introduce a contrast or exception.** If the previous paragraph ends with a problem, the next paragraph opens by naming what addresses it — not by introducing a new concept cold. Never start a paragraph with a new term or mechanism that hasn't been set up by what came before. Before writing any paragraph, ask: what did the reader just learn, and how does this paragraph follow from that? A paragraph that could appear anywhere in the section is a broken transition. Within a paragraph, use connective words ("However," "But," "That said") when moving from a category to an exception — without them, consecutive sentences read as disconnected facts. Example: "Non-retryable: 400, 401, 403, 404. However, client-side errors don't resolve on retry." Not: "Non-retryable: 400, 401, 403, 404. Client-side errors don't resolve on retry."

### Sedai Placement
- Sedai appears **once** in the body, tied to a specific outcome with a named source
- The post answers the reader's question — it is not a pitch
- If a section could only appear on Sedai's website and nowhere else, it is a pitch and must be rewritten

### Use Cases
- Every use case must be backed by a real customer, a published case study, or a named source
- Do not write illustrative/hypothetical scenarios with specific numbers attached — a made-up scenario with real numbers implies specificity that isn't there and is worse than no number at all
- If no real use cases are available, either omit the section or write the scenarios without any specific figures and frame them explicitly as representative patterns, not customer stories

### Hard Stops — Never Do These
- No colon in H1 or any H2
- No em dash in H1 or H2
- Maximum 3 em dashes in the entire post — find alternatives: rewrite as two sentences, use a comma, use a colon, or restructure the clause
- No subtitle pattern in H1 ("What is AI Tokenomics: The Complete Guide")
- No Cast AI references or links
- No GigaOm references unless the brief explicitly requires it for a specific contextual reason
- No "visibility" as a Sedai value prop
- No "LLM optimization" as a category label — use "AI agent optimization"
- No Challenge / Approach / Outcome section structure
- No generic CTAs unrelated to the post topic
- Do not use "It wasn't about X, it was about Y" constructions

### Required Elements
- Named author: full name, title, LinkedIn URL
- Publish date + Last Updated date visible
- FAQPage section: minimum 5 questions, each answer 2–3 sentences, self-contained
- Any table with pricing or time-sensitive data: datestamped title (e.g., "AI model pricing by provider — June 2026")
- Meta title and meta description matching the brief spec

---

## Step 3: Claim Audit Before Output

Before outputting the draft, run this check:

Extract every statistic, metric, percentage, and quantified claim from the draft. For each one, confirm it appears in your sourcing table from Step 1 with a verified primary source URL. If anything in the draft is not in the sourcing table, either add it to the sourcing table with its source or remove it from the draft.

Do not output a draft with unverified claims.

---

## Step 4: Output

Output two things:

**1. The draft** — full, publish-ready, formatted in Markdown with all H1/H2/H3 structure, tables, and FAQ.

**2. The sourcing table** — every claim in the post with its source and URL:

| Claim | Source | URL | Status |
|---|---|---|---|
| "Monthly token spend increased 13x..." | Sedai webinar data, June 2026 | Internal | Verified |
| "Goldman Sachs projects 24x token growth..." | FinOps X 2026 recap | [url] | Verified |
| "A third of LLM costs were optimizable" | Notes From Suresh, Sedai | Internal | Verified |
| "Cache hit rates of 60–80% realistic" | — | — | NEEDS SOURCE |

Any row with NEEDS SOURCE must also appear as a note at the top of the draft: "The following claims require engineer input or a primary source before publish: [list]."

---

## Reference Files

- `references/sedai-rules.md` — Full rules checklist for structure, voice, and hard stops
- `/Users/emkochanek/.claude/skills/sedai-shared/shared-data.md` — Keyword clusters, VOC, messaging, approved claims
- `/Users/emkochanek/Desktop/CONTENT MARKETING MASTER - CLAUDE/Marketing Messaging MASTER 2026/SEO KWs/` — Source of truth for all keyword data
