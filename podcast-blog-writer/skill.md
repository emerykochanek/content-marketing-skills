---
name: podcast-blog-writer
description: Write a blog post based on a podcast episode transcript or notes. Produces a SEO-grounded, editorially strong post for engineering-leader audiences — not a transcript summary or show notes. Use when the user provides a transcript, episode title, or rough notes and wants a published-quality blog post. Optimized for 1 IDEA podcast topics: AI, cloud, DevOps, SRE, platform engineering, FinOps, autonomous operations, and infrastructure.
---

# Podcast Blog Writer

## Goal
Turn a podcast episode into a standalone, search-discoverable blog post that works for readers who never heard the episode. The post should be editorially strong — a real piece of writing with a thesis, tension, and resolution — not a formatted summary.

It should also be findable. Use search-intent framing, keyword-aware headings, and structured content that search engines and AI citation engines (Google AI Overviews, ChatGPT, Perplexity) can parse and quote.

## The Audience
Engineering leaders and senior practitioners: Staff and Principal Engineers, CTOs, VPs of Engineering, DevOps, SRE, Platform, Cloud, FinOps. They read blog posts to answer a specific question or validate a decision. They skip posts that take three paragraphs to get to the point. They share posts that say something true and specific.

## What Makes a Good Episode Blog Post

Strong:
- Has a clear thesis — one thing the episode argues that a reader might disagree with
- Opens with the problem, not with the guest's bio or episode framing
- Uses the guest's specific insights as evidence, not decoration
- Is useful to someone who never listens to the podcast
- Ends with a specific takeaway or tension — not "the future is exciting"

Weak:
- Is a transcript with section breaks
- Opens with "In this episode of 1 IDEA..."
- Lists everything the guest said without a through-line
- Uses the episode as the subject ("the episode covers...") instead of the ideas as the subject

## Working Process

### 1. Identify the Thesis
Before writing, extract the episode's core argument in one sentence.

Ask: if a senior engineer read nothing but the headline and first paragraph, what claim would they walk away with?

The thesis should be specific enough to be wrong. "AI is changing everything" is not a thesis. "Most AI cost problems are really resource tagging problems" is.

### 2. Identify the Three Supporting Ideas
Find the three most concrete sub-claims that support the thesis. These become the H2 sections. They should be distinct — not three ways of saying the same thing.

### 3. Map SEO Intent
Determine what a practitioner would search for to find this post. The post should rank for a specific, answerable question — not a broad category.

Good target intents:
- "how to reduce AI inference costs in production"
- "kubernetes autoscaling strategies for bursty workloads"
- "when to use agents vs workflows in AI systems"
- "platform engineering team structure"

Avoid targeting:
- Brand terms (podcast name, guest name) as the primary keyword
- Generic category terms ("AI," "DevOps," "cloud cost") without a specific angle

Use the target intent to:
- Frame the H1/title (should match the search intent)
- Write the meta description (concise, factual, 120–155 characters)
- Choose H2 headings that answer sub-questions a searcher would have

### 4. Structure the Post

**Recommended structure for a 900–1400 word post:**

1. **Title (H1)** — Search-intent-aligned, specific, under 65 characters
2. **Lede (1–2 paragraphs)** — State the problem. No episode framing. No biography.
3. **[H2] First supporting idea** — 150–250 words. One concrete insight from the episode.
4. **[H2] Second supporting idea** — 150–250 words. A distinct second claim.
5. **[H2] Third supporting idea** — 150–250 words. Often the most actionable section.
6. **Takeaway / What to do** — 100–150 words. A specific action or decision framework. Not a summary.
7. **Episode note** — 1–2 sentence attribution. "This post is based on a conversation with [Guest] on the 1 IDEA podcast. [Link placeholder]"

Do not include a summary section or repeat the lede at the end. End with the takeaway.

### 5. Write to Citation Standards
AI Overviews and AI search engines prefer content that:
- Defines terms clearly in the first mention
- Answers a specific question directly within the first 100 words
- Uses numbered or bulleted lists for steps, comparisons, and decision criteria
- Contains at least one passage that could stand alone as a factual answer (a "passage-level citation" — typically 2–4 sentences)

Apply this by:
- Including one short definition or "what this means" box for any jargon
- Writing at least one section with a clear 3–5 item list (not decorative — genuinely useful for scanners)
- Making sure the lede directly answers the implied question in the title

**Section extractability rule:** The first 40–60 words after each H2 heading are the highest-value real estate on the page. AI systems pull from opening statements more than any other part of a section. Every H2 section must answer its implied question in its opening sentence and be able to stand alone as a complete answer without surrounding context.

Before finalizing, apply this test to each H2 section: can it be extracted and read independently — with no knowledge of the sections before or after it — and still be a complete, useful answer? If yes, the structure is extraction-ready. If no, rewrite the opening sentence to front-load the answer.

## Output Format

Provide the full post, ready to copy into a CMS, structured as:

```
---
Title: [H1]
Meta description: [120–155 characters]
Target keyword: [primary search phrase]
---

[Post body with H2 headings, as described above]

---
*This post is based on a conversation with [Guest Name], [Title] at [Company], on the 1 IDEA podcast. [Link placeholder]*
```

After the post, add a brief editorial note (not part of the post):

**Editorial note:**
- **Thesis:** [one sentence]
- **Primary keyword target:** [phrase]
- **Strongest passage for AI citation:** [quote the 2–4 sentence block most likely to be cited]
- **One thing to verify:** [any claim from the transcript that should be fact-checked before publishing]

## Title Writing Rules

The H1 title should:
- Match the search intent, not the podcast episode title
- Be specific enough to promise a concrete answer
- Be under 65 characters
- Avoid question format unless the post answers a genuinely debated question

Good title examples:
- How to Reduce AI Inference Costs Without Sacrificing Latency
- Why Platform Teams Fail at Developer Experience (And How to Fix It)
- The Case Against Kubernetes for Small AI Workloads
- When AI Agents Need Human Escalation

Weak title examples:
- The Future of AI Infrastructure
- Insights From a CTO on AI
- What We Learned About Cloud Cost

## Writing Style Rules

- Write in third person unless the post is framed as an opinion piece
- Use the guest's name and direct quotes sparingly — they add credibility but should not carry the argument
- Do not use bullet points as a substitute for writing — if an insight needs explanation, write a paragraph
- Avoid filler phrases: "at the end of the day," "it's important to note," "in today's landscape," "the bottom line is"
- Avoid vague adjectives: "robust," "seamless," "powerful," "innovative," "cutting-edge"
- A short sentence is almost always better than a long one
- If a section is weak, it is usually because the underlying claim is weak — fix the claim, not the prose

## Length Guidelines

- Standard post: 900–1,200 words
- Deep-dive post (if user asks): 1,400–2,000 words with additional H2 sections or a "Deeper Look" subsection
- Short-form post (if user asks for a quick take): 500–700 words, one H2 per supporting point

Default to standard unless the user specifies otherwise.
