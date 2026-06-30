# Sedai Topic Selection & Brief Generator

## What this skill does
Runs a full monthly content research cycle and outputs ready-to-send content briefs for the Sedai blog. Replaces ad hoc agency topic selection with a data-driven, bucket-based system grounded in AEO/GEO/SEO research, live competitor analysis, VOC data, and Sedai's own site inventory.

## How to use
Tell the skill how many briefs you need and which buckets to prioritize. The skill handles all research automatically before outputting briefs. Optionally paste in Semrush CSVs or Atlas data if you have them — the skill will use them alongside its own pulls.

---

## STEP 0: Load Shared Data

Before any research or topic selection, read `/Users/emkochanek/.claude/skills/sedai-shared/shared-data.md`. This file is the single source of truth for all keyword clusters (9 clusters with volumes), VOC language, messaging guide, approved claims, and hard stops. The cluster data in this skill file is authoritative but the shared file may have been updated since. Load it first — do not rely on memory or the summaries below alone.

---

## STEP 1: Automated research (skill runs this before selecting topics)

The skill always runs these checks before proposing any topic. Do not skip any step.

**1. Sybill VOC pull**
Query Sybill for:
- Exact phrases prospects and customers used this month about pain points, problems, and goals
- Any new competitor tools mentioned on calls
- Any new objections that don't have a content answer yet
- Language around cost, governance, observability, scaling, and reliability
Use verbatim Sybill language in briefs — never paraphrase VOC into generic marketing language.

**2. Sedai site inventory check**
Before recommending any new page, confirm it doesn't already exist:
- Read `/Users/emkochanek/Desktop/CONTENT MARKETING MASTER - CLAUDE/Sedai_Keyword_Blog_Audit.md`
- Cross-reference against the Keyword-Topic Master Map below
- Distinguish between: (a) page exists and ranks, (b) page exists but doesn't rank for this term, (c) no page exists
Never recommend a new page for a term where a page already exists — recommend a Refresh refresh instead.

**3. Competitor content check**
For any topic being considered, check what Cast AI, ScaleOps, and PerfectScale have published:
- Search "[topic] site:cast.ai" and "[topic] site:scaleops.com"
- Note their H2 structure, word count, and angle
- The brief must explain specifically how Sedai's post will out-answer theirs for AI citation — not just cover the same ground

**4. Semrush keyword data**
If CSVs are provided, use them. If not, note which terms need volume data before briefing.
- Flag any money keyword that dropped more than 5 positions — those need urgent content
- Flag any term where a competitor ranks top 5 and Sedai is absent
- Always use real volume numbers in briefs — never write "low" or "moderate" without the actual figure

**5. Atlas theme health**
If Atlas data is provided, use it. Flag any theme showing "Needs Attention" or "Poor" that Sedai should own.

---

## STEP 1b: SERP + AI Platform Research (run on ALL candidate topics)

Before ranking or selecting final topics, run live SERP and AI platform research on every topic the longlist contains. Do not skip topics based on intuition — SERP data determines which topics are winnable and how to angle them.

**For each candidate topic, run seo-sxo on the primary query. Capture:**
- Dominant page type and H1 pattern winning in SERP
- Featured snippet language pattern (exact text, not just format — quote actual words/phrases if a snippet exists)
- PAA questions (minimum 5)
- Related searches
- Top 3 competing pages: URL, H2 structure, what they cover, what they miss
- Competitive structure requirements: H2 sections present in 3+ ranking pages
- SERP gap: any angle unoccupied in the top 10 that Sedai could own

**For each candidate topic, run AI platform monitoring — query each platform with the exact topic and capture:**

| Platform | What it says | Sources it cites | Language it uses | What's missing |
|---|---|---|---|---|
| Perplexity | | | | |
| ChatGPT | | | | |
| Gemini | | | | |
| Claude | | | | |

**Cross-platform patterns to record:**
- Language used by 3+ platforms → use in H2s and section openers for this topic
- Sources cited by 3+ platforms → pages to beat for AI citation
- Gaps in all platform answers → content angles Sedai could own

**How this data feeds topic selection:**
- Topics where Sedai can fill AI citation gaps get higher priority
- The angle for each brief leads with what the AI platforms are missing
- H2 phrasing mirrors language the platforms already use — not invented editorial labels

---

## STEP 2: Specify your output

Tell the skill:
- How many briefs you need (recommend 4-6 per month)
- Which buckets to prioritize (see bucket definitions below)
- Any topics the agency has already proposed (skill will evaluate and keep/replace them)
- Any Semrush CSVs or Atlas exports to incorporate

---

## STEP 3: The skill outputs briefs

Using all research above, the skill:
1. Pulls Sybill VOC and surfaces new language, objections, and competitor mentions
2. Checks Sedai site inventory — no duplicate page recommendations
3. Checks what competitors have published on shortlisted topics
4. Selects topics by tier priority (see Topic Selection Logic below)
5. Applies the keyword-topic map to check what's already in-flight
6. Outputs one complete brief per topic, with real keyword volumes and VOC language baked in

---

## The Five Content Buckets

**Best-of Listicles**
Format: "Best [X] tools for [Y]", "Top [X] platforms for [Y] in 2026"
Purpose: Listicles account for 40.9% of commercial query AIO citations (Wix Studio, 75,000 AI answers). Third-party editorial listicles capture 80.9% of professional services citations vs. 19.1% for brand-created rankings — AI systems prefer neutral editorial framing. Sedai has almost no listicle content.
Volume: 1-2 per month
Examples: "Best Kubernetes Cost Management Tools for 2026", "Best Pod Rightsizing Tools Compared", "9 Best Kubernetes Cost Optimization Tools for Platform Teams in 2026"

**Comparison / VS / Alternatives**
Format: "[Tool] alternatives", "[Tool A] vs [Tool B]", "Best [Tool] alternatives for [use case]"
Purpose: Directly competes in the "Logan Prompts" theme — the highest-intent queries buyers use mid-evaluation. Comparison pages convert at 5–10x vs. general organic traffic. Sedai is nearly invisible here.
Volume: 1-2 per month
Freshness requirement: Quarterly refresh. Comparison content sees a 40% citation drop when updates lapse beyond 6 months.
Examples: "Cast AI Alternatives for EKS", "Kubecost vs OpenCost", "Karpenter vs Cluster Autoscaler", "Sedai vs Cast AI"

**Category Ownership**
Format: "What is [concept]", "How [Sedai-invented concept] works", definitional guides
Purpose: Sedai invented autonomous cloud optimization. No competitor has claimed this in AI citation. These pages become the source AI systems cite when defining the category. The short-answer definition block is the highest-value AI extraction element on any page.
Volume: 1 per month
Examples: "What Is Autonomous Cloud Optimization?", "Autonomous vs Automated Cloud Management: What's the Difference?"

**Practitioner Guides**
Format: "How to [do specific thing] without [fear/risk/manual work]", OR problem-first: "[Topic]: Why It Fails in Production and How to Fix It"
Purpose: These match the exact language buyers use mid-investigation. Troubleshooting sections are among the highest-value AIO and Perplexity citation targets. Perplexity heavily cites troubleshooting-formatted content. Atlas shows Sedai's highest brand visibility (40-66%) is on ECS and autonomous Kubernetes queries.
Volume: 2-3 per month
Examples: "Kubernetes HPA: Why It Fails in Production and How to Fix It", "How to Right-Size Kubernetes Nodes Without Downtime", "Pod Disruption Budgets: Common Misconfigurations and How to Fix Them"

**Refresh**
Format: AEO/GEO structural improvements to posts already ranking or previously ranked
Purpose: Structural AI-readability determines citation independent of ranking position. Pages that rank on page 1 do not automatically get cited. A systematic structural refresh (10-step checklist in brief) can recover collapsed rankings and activate AI citation without full production cost.
Volume: 2-4 refreshes per month
Priority criteria: Pages that dropped more than 5 positions in money keywords, or pages ranking 10-30 with no AI citation.

---

## Keyword-Topic Master Map (reference when selecting topics)

This is the complete keyword cluster map. Check it before selecting any topic — it shows what's in flight, what's been covered, and what the highest-priority gaps are.

**Cluster 1: Kubernetes Cost Optimization Head Terms (Tier 1 — ~3,880 combined vol)**
Status: COLLAPSED. No in-flight content.
Keywords: kubernetes cost optimization (1,560), kubernetes cost management (590), kubernetes cost monitoring (480), kubernetes billing (880), kubernetes pricing (200)
Hub page needed: Comprehensive 12,000–16,000 word pillar guide. HIGHEST PRIORITY CONTENT ACTION.

**Cluster 2: Kubernetes Autoscaling (Tier 1 — ~3,590 combined vol)**
Status: Underranking or zero. HPA vs VPA (170 vol) in flight June 2026.
Keywords: kubernetes hpa (880), hpa kubernetes (720), kubernetes cluster autoscaler (480), horizontal pod autoscaler (390), cluster autoscaler (480), autoscaler kubernetes (210)
Needed: Dedicated HPA practitioner guide (distinct from HPA vs VPA comparison), Cluster Autoscaler guide rewrite (existing page at rank 70 — do NOT change URL)

**Cluster 3: Pod Rightsizing (Tier 2 — ~480 combined vol)**
Status: Rank 13 for tools; "automate pod rightsizing" in flight June 2026.
Keywords: pod rightsizing platforms (260), pod rightsizing tools (90), in-place pod resize (60)
Needed: Pod rightsizing tools listicle (Best-of Listicle), in-place pod resize guide (Practitioner Guide)

**Cluster 4: Kubernetes Resource Management (near-Tier 1 — ~940 vol)**
Status: Rank 0 across the board, nothing in flight.
Keywords: pod disruption budget (590), kubernetes node affinity (210), kubernetes limits vs requests (110)
Note: 590 vol with rank 0 is severely underaddressed. Pod disruption budget is near-Tier 1 by volume.

**Cluster 5: Kubernetes Cost Tools (Tier 2 — ~460 combined vol)**
Status: Not ranking, nothing in flight.
Keywords: best kubernetes cost management tools (200), kubernetes resource optimization tools (130), best kubernetes cost optimization tools (130)
Needed: Consolidated tools listicle targeting all three keyword variants (one post, not three)

**Cluster 6: Cloud Cost Optimization — Collapsed Money Terms (Tier 1 — ~3,700 vol)**
Status: COLLAPSED. Existing pages only.
Keywords: cloud cost optimization (2,400), finops tools (480), multi cloud cost management (390), cloud optimization services (260)
Action: Refresh refresh only. Do NOT create new pages for these terms — refresh existing pages.

**Cluster 7: AWS/Azure — Never Ranked (Tier 1)**
Status: Never ranked. ECS cost optimization in flight June 2026.
Keywords: aws cost optimization, aws cost management, azure cost optimization
Action: New Practitioner Guide guides per platform.

**Cluster 8: Category Ownership (Tier 1 — Strategic)**
Status: Not ranking, nothing in flight.
Keywords: autonomous cloud optimization, what is autonomous optimization
Action: Category Ownership definitional post. Low current search volume but critical for AI citation anchoring.

**Cluster 9: AI Agent Optimization (Tier 1 — Emerging, HIGH PRIORITY)**
Status: Net-new category. Sedai launched AI Agent Optimization in preview June 8, 2026. Zero existing Sedai pages. No competitor has a definitional page for this term yet.

Semrush data (June 16 2026):
- llm routing: 170/mo, KD 50 — highest volume, most competitive
- llm cost optimization: 40/mo, KD 15 — Cast AI ranks #1, Sedai absent
- ai agent optimization: 30/mo, KD 24 — trending to 1.00, growing
- llm governance: 30/mo, KD 19 — trending to 1.00, growing
- ai agent cost optimization: 10/mo, KD 14
- ai agent governance tools: 10/mo, KD 35
- reduce llm costs: 0 volume currently
- pointfive alternatives, aws finops agent alternative, best ai agent cost optimization tools, model routing kubernetes, what is ai agent optimization: no volume data yet (too new)
All terms show AI Overview in SERP — confirms GEO/AEO priority over traditional SEO volume.

Confirmed keywords (Semrush + Sybill validated):
- ai agent optimization, what is ai agent optimization
- llm cost optimization (Cast AI owns — differentiate on accuracy + cost, not cost-only)
- llm governance
- llm routing / smart routing for llm calls
- ai agent cost optimization
- reduce llm costs / token utilization
- pointfive alternatives
- aws finops agent alternative
- best ai agent cost optimization tools
- model routing kubernetes

VOC additions from Sybill (June 16 2026 — verbatim prospect language):
- "observability and governance for AI agents" — prospects use these two words together
- "visibility and optimization for how teams are using AI" — awareness + action framing
- "smart routing for LLM calls to optimize for accuracy, cost, and performance" — exact phrase
- "governance rules — allow lists, deny lists, fallback models" — enterprise governance language
- "steer prompts to smaller cheaper models when task doesn't require high-end model" — routing value prop
- "token utilization — need to be more mindful about it" — FinOps framing
- "FinOps capabilities to track and manage spend across different AI models and API providers"
- "prevent runaway costs if an agent gets stuck in a loop calling an expensive API" — specific fear
- "data residency capabilities" — compliance angle, enterprise deals
- "FedRAMP certification" — federal/regulated industry angle
- "on-prem deployment or private instance" — air-gapped / compliance requirement

VOC-derived keyword additions to run through Semrush:
- llm observability
- ai agent cost control
- llm model selection
- ai compliance llm
- prompt cost optimization
- fedramp llm
- token cost management
- ai governance platform
- llm spend management
- runaway ai costs

Audiences: Platform Engineering, FinOps, ML/AI Engineers
Datadog note: Comes up in almost every call as the existing observability tool. Sedai integrates with Datadog — do NOT position against it. Frame as "works alongside your existing Datadog setup."

Competitive context: PointFive ($60M Series B June 2026) creates tickets, requires humans, no application awareness. Cast AI "LLM Optimization" is a gateway/proxy model (cost-only, not accuracy + cost). AWS FinOps Agent (June 2026) is reactive, AWS-only, routes to Jira. Datadog DASH visibility-only — and is the incumbent tool in most prospect stacks. Martian = closest Smart Routing competitor but not self-serve.
Sedai differentiators: Full-stack (only platform covering infra + agent layer), per-agent routers not universal, autopilot not toolkit, dynamic/self-improving, self-serve, one import zero rewrites.

In-flight July 2026:
  - "What is AI Agent Optimization?" (Category Ownership, Week 1)
  - "Sedai vs PointFive" (Comparison, Week 1) — time-sensitive, PointFive Series B announced
  - "AWS FinOps Agent vs Sedai" (Comparison, Week 2) — time-sensitive, AWS launched June 9
  - "How to Reduce LLM Costs Across a Multi-Agent Platform" (Practitioner Guide, Week 2)
  - "Best AI Agent Cost Optimization Tools 2026" (Best-of Listicle, Week 3)

Future content angles (VOC-driven, not yet briefed):
  - "LLM Governance: Allow Lists, Deny Lists, and Fallback Models Explained" (Category Ownership / Practitioner Guide)
  - "How to Prevent Runaway AI Agent Costs" (Practitioner Guide) — exact fear from calls
  - "LLM Observability vs AI Agent Optimization: What's the Difference?" (Category Ownership)
  - "AI Compliance for LLMs: Data Residency, FedRAMP, and On-Prem Options" (Practitioner Guide) — enterprise angle

Comparison pages to build eventually: Sedai vs Martian, Sedai vs Cast AI LLM Optimization, Sedai vs PortKey
Do NOT use "LLM Optimization" as the category label — that is Cast AI's term. Always use "AI Agent Optimization."
Do NOT position against Datadog — integrate/complement framing only.

---

## Topic Selection Logic (how the skill prioritizes)

**Tier 1 — Must address:**
- Any Atlas theme showing "Needs Attention" or "Poor" that Sedai should own
- Any money keyword that dropped more than 5 positions
- Any Tier 1 keyword cluster with no in-flight content
- Any bucket that received zero new content in the prior month

**Tier 2 — Should address:**
- Keyword gaps where a direct competitor (Cast AI, ScaleOps) ranks in top 5 and Sedai is absent or below rank 20
- VOC phrases from Sybill that have no corresponding blog content

**Tier 3 — Nice to have:**
- Emerging topics from Sybill (new competitor tools mentioned, new trigger events)
- ScaleOps/Cast AI content that Sedai has no counter for

---

## Topic Brief Template (output for each selected topic)

The skill outputs one brief per topic in this format:

---

### BRIEF: [Topic Title]

**Bucket:** [Which of the 5 buckets]
**Primary target query:** [The exact query this post is built to answer in AI and search]
**Format:** [Listicle / Comparison / Guide / Definition]
**Word count:** [Target — by bucket: Listicle 2,000-3,500 / Comparison 1,800-3,000 / Definitional 1,500-2,500 / Practitioner guide 2,000-5,000 / Pillar guide 12,000-16,000]
**Why this topic now:** [One sentence tying to Atlas data, keyword gap, or VOC signal]

**AI Platform Signal:** [What Perplexity, ChatGPT, Gemini, and Claude are currently saying about this topic — what sources they cite, what language they use, what's missing from their answers that Sedai could provide. This is the citation gap the brief will fill.]

**The angle:**
[One sentence on what makes this different from what already ranks. Not a topic description — a specific editorial stance. Example: "Most 'Kubecost alternatives' posts list tools with similar dashboards. This one argues that the real alternative to Kubecost isn't another visibility tool — it's a system that acts on what it sees."]

**Who this is for:**
[Specific persona — not "enterprise IT." Example: "Platform engineer at a 200-500 person company managing ECS workloads, getting pressure from finance to explain a spike in AWS spend, doesn't have a dedicated FinOps team."]

**VOC language to use:**
[3-5 specific phrases from Sybill data relevant to this topic. These should appear in section openers, product proof sections, and the intro.]
- "[phrase 1]"
- "[phrase 2]"
- "[phrase 3]"

**Pages to beat:**
[Top 2-3 URLs currently ranking for the primary query. Writer's job: out-answer these for AI citation.]
1. [URL] — what it does well, what it's missing
2. [URL] — what it does well, what it's missing

**Key claims to make (with evidence):**
[The 3-4 factual statements this post must make. Each claim needs a source — Sedai product capability, third-party stat, or customer outcome.]
1. Claim: [statement] | Evidence: [source]
2. Claim: [statement] | Evidence: [source]
3. Claim: [statement] | Evidence: [source]

---

## Required AEO/GEO Structure (apply to every bucket)

These rules are derived from peer-reviewed GEO research and competitor structural analysis. They override all style guide conventions for blog content.

### Rules with strong research backing

**Passage-level optimization:**
- Every H2 section must be answerable without reading the sections before or after it (self-contained)
- Evidence density over formatting: include 3–5 statistics per 1,000 words with specific numbers and timeframes
- Cite primary sources inline (not in a references section at the bottom) — Princeton GEO found this produces +30–40% AI visibility
- Code examples increase citation influence +77%, statistics +62%, definitions +57%, comparisons +55% (citation absorption study, 2026)
- Q&A formatting alone produced -5.74% citation influence — FAQ structure belongs in a dedicated FAQ section, not throughout the body

**H2 headings:**
- Each H2 should function as an independent sub-query anchor (Google's AI Mode decomposes queries into "dozens, sometimes hundreds of sub-queries")
- First sentence after every H2 must state the direct answer — no throat-clearing, no "in this section we will explore"
- For AEO/GEO: mirror exact query phrasing in H2s where possible
- High-influence pages have 12.5x more headings than low-influence pages — more H2s = more citation surface area

**Author and freshness:**
- Named author with specific credentials on every post (title, expertise domain) — improves citation rates from 28% to 43%
- Visible "Last Updated" date — 1.8x more citations for pages with visible timestamps

### Rules by bucket

**Best-of Listicles:**
- "How We Evaluated These Tools" H2 is required — signals editorial neutrality to AI systems
- Comparison table must appear before individual tool entries, not after
- Required table dimensions: automation level (autonomous/advisory/visibility-only), self-hosted option, multi-cloud support, rightsizing method, pricing model, best for
- Cast AI avoids comparison tables — Sedai should always use one (this is a competitive gap)
- FAQPage schema with minimum 5 questions
- Table of contents for any list over 8 tools
- Year in H1 and meta title

**Comparison / VS / Alternatives:**
- TL;DR block (40–60 words, independently extractable) immediately following the H1 is the highest-impact AIO element on comparison pages
- Acknowledge competitor strengths honestly — pages that acknowledge tradeoffs outperform "we win everything" pages for AI citation
- Include specific pricing numbers wherever available (comparison content with pricing specifics earns far more AI citations than "contact sales")
- Dedicated URL structure: /compare/tool-a-vs-tool-b/ or /alternatives/tool-name/
- Quarterly freshness required — 40% citation drop when updates lapse beyond 6 months

**Category Ownership — Definitional:**
- Short-answer definition block (60 words max) immediately after H1 — this is the highest-ROI element on the page. Pattern: "[Term] is [clear, standalone definition]."
- Must include a contrast section with the adjacent/competing term
- Avoid hedging language ("might," "perhaps," "could potentially") — Princeton GEO found authoritative voice produces +10–20% citation lift

**Practitioner Guide:**
- Prerequisites block required — lists tools, access levels, versions needed; creates a self-contained, AI-extractable section
- Code blocks with actual commands required — absence of commands signals low expertise and kills dwell time
- Troubleshooting H2 required — name failure modes explicitly in H3s; this is among the highest-value Perplexity citation targets
- Verification H2 required ("How to Confirm It Worked") — highly cited in AI Overviews
- Problem-then-Fix H2 pattern (proven by ScaleOps' structure): name the failure mode first, then the fix
- Real customer cost reduction figures from Sedai data are more valuable than generic benchmarks for AIO/ChatGPT citation

**Refresh:**
- Do NOT change the URL
- Minimum 15–20% substantive content change required for AI systems to register as meaningful update
- Full 10-step checklist: (1) update statistics, (2) restructure into 120–180 word self-contained sections, (3) add/rebuild comparison table, (4) add/expand FAQ block, (5) rewrite section openers to lead with answer, (6) add author credentials, (7) implement schema, (8) add quote-ready standalone sentences, (9) cite primary sources inline, (10) add "Last Updated" timestamp

### Rules that do NOT apply to agency blog content

Per Em Kochanek's explicit instruction: Sedai Messaging Guide and Sedai Style Guide style rules do not govern blog content structure. The following are specifically prohibited:

- 1–2 sentence paragraph rule (paragraphs can be 3–4 sentences per SEO research)
- Slashes for descriptions
- Standalone "Challenge / Approach / Outcome" sections
- Customer quotes that don't directly support a claim in that section
- "Visibility" as a value prop (that's what buyers are leaving behind)
- Generic CTA not related to the article topic
- Em's editorial H2 style (claims, imperatives, rhetorical questions) — agency posts should mirror competitor H2 patterns

The Sedai Messaging Guide IS useful for: which differentiators to claim, what the "monster" is (blind risky automation), what Sedai's category is (autonomous cloud optimization, the self-driving cloud), which proof points to use (application-aware intelligence, outcome-driven optimization, safe autonomy, full-stack coverage, enterprise governance).

---

## Schema requirements (apply to every post)

- Article schema with dateModified: every post
- FAQPage schema: every post with a FAQ section (minimum 5 questions per FAQ)
- HowTo schema: every step-by-step guide (Practitioner Guide)
- Product schema: every tool or product mentioned in a comparison/alternatives page

Note: Schema does not directly boost AI citation rates (Ahrefs study, 1,885 pages, August 2025–March 2026). Implement as table stakes for traditional SEO and rich results, not as an AI visibility lever.

---

## Title rule (research-backed — apply to every brief)

Blog post titles must match the target search query as closely as possible.
- If the query is "what is llm routing" the title is "What is LLM Routing?"
- If the query is "how to reduce llm costs" the title is "How to Reduce LLM Costs"
- If the query is a listicle: "Best AI Agent Cost Optimization Tools 2026" — default no colon
- If the query is a comparison: "Sedai vs PointFive" — default no colon

**Colon rule:** Default to no colon in titles. A colon is allowed only if seo-sxo SERP research confirms the colon format is what wins for that specific query — and even then, use sparingly. Generic subtitle patterns ("X: Why It Matters," "X: What It Is and How It Works") are never acceptable regardless of SERP data.

NO subtitles. NO "X: Why It Matters" or "X: What It Is and How It Works" patterns — ever.
Source: Answer-first headlines cited 41% vs 29% for loosely related headlines (Ahrefs 2026).

---

## Hard stops — do not include

- Standalone "Challenge / Approach / Outcome" section
- Customer quotes that don't directly support a specific claim in that section
- Methodology stats or product stats dropped in without connection to the article topic
- "Visibility" as a value prop
- Generic CTA not related to the article topic
- Slashes for descriptions
- Colons in post titles unless seo-sxo SERP research confirms the colon format wins for that specific query
- Generic subtitle patterns after post titles ("X: Why It Matters" etc.) — never, regardless of research
- Subtitles after post titles
- Claude-style H2s (long, vague, colons, clichés, generic) — H2s should mirror competitor patterns; H2 colons are never acceptable

---

## Internal links to include

[2-3 existing Sedai posts that are topically relevant — keeps link equity flowing to rankers. Every post must link back to the hub pillar guide once it exists.]

**Author:**
[Name and title — must be a real Sedai person with relevant credentials. Include title and specific expertise domain (e.g., "Staff Platform Engineer at Sedai, 8 years in Kubernetes infrastructure"). Link to LinkedIn. No dedicated bio page needed.]

---

## Context files to reference when running this skill

- `/Users/emkochanek/Desktop/CONTENT MARKETING MASTER - CLAUDE/Voice_of_Customer_Sybill.md` — current VOC language
- `/Users/emkochanek/Desktop/CONTENT MARKETING MASTER - CLAUDE/Sedai_Keyword_Blog_Audit.md` — keyword gaps and existing content inventory
- `/Users/emkochanek/Desktop/CONTENT MARKETING MASTER - CLAUDE/Research/Sedai_Content_Research_Foundation.md` — full research foundation (competitor map, bucket structures, keyword clusters, evidence-graded rules)
- Atlas CSV files in Research folder — for current theme performance data
