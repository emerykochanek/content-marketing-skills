# Content Marketing Skills

Custom Claude Code skills for content and marketing work.

---

## What this is

These are slash commands that run inside [Claude Code](https://claude.ai/code). Each skill is a set of instructions that tells Claude how to do a specific marketing task — packaging a podcast episode for YouTube, writing a blog post from a transcript, finding clips, etc.

They are not prompts you paste. They are installed once and then available as `/skill-name` commands in any Claude Code session.

---

## How to install

**Step 1 — Install Claude Code**

Download it at [claude.ai/download](https://claude.ai/download) and sign in with your Anthropic account.

**Step 2 — Open Terminal**

On a Mac, press **Command + Space**, type **Terminal**, hit Enter.

**Step 3 — Clone the repo**

```
git clone https://github.com/emerykochanek/content-marketing-skills.git
```

**Step 4 — Copy the skills into Claude Code**

```
cp -r content-marketing-skills/* ~/.claude/skills/
```

**Step 5 — Test it**

Open Claude Code, start a new conversation, and type `/podcast` — the skills should appear in the menu.

---

## How to get updates

```
cd content-marketing-skills
git pull
cp -r * ~/.claude/skills/
```

---

## Skills

### Podcast

| Skill | Command | What it does | Input |
|---|---|---|---|
| YouTube Packager | `/one-idea-youtube-packager` | Title, thumbnail, description, and chapter options for a YouTube upload. Scored report with final recommendation. | Episode transcript |
| Blog Writer | `/podcast-blog-writer` | Standalone SEO blog post from the episode — not a transcript summary. | Episode transcript or notes |
| Clip Finder | `/podcast-clip-finder` | Finds the 3–6 best short-form clips. For each: timestamps, what to cut, LinkedIn caption, YouTube Short title. | Episode transcript |
| Interview Brief | `/podcast-interview-brief` | Pre-interview brief: episode thesis, cold open intro, host overview, 7–10 questions with follow-up probes. | Guest background, article, talk, or rough notes |

### SEO

| Skill | Command | What it does | Input |
|---|---|---|---|
| SEO/SXO | `/seo-sxo` | Reads Google SERPs to detect page-type mismatches, derives user stories from search intent, scores pages from multiple persona perspectives. | Keyword or URL |

### Content (Sedai)

| Skill | Command | What it does | Input |
|---|---|---|---|
| AEO Blog | `/sedai-aeo-blog` | Full content review for Sedai blog posts against SEO/GEO/AEO research, keyword clusters, messaging guide, and VOC language. | Draft or URL |
| Blog Writer | `/sedai-blog-writer` | Writes Sedai blog posts grounded in AEO/GEO/SEO research. | Brief or topic |
| Content Brief | `/sedai-content-brief` | SEO/GEO/AEO-optimized content briefs for Sedai blog posts. | Topic or keyword |
| Topic Selection | `/sedai-topic-selection` | Selects and prioritizes content topics based on keyword clusters and content strategy. | — |

### Case Studies

| Skill | Command | What it does | Input |
|---|---|---|---|
| Case Study | `/case-study` | Full-lifecycle B2B case study: pre-interview questions, PSR-structured draft, multi-channel distribution plan. | Customer name, context, or interview transcript |

---

## Questions

Reach out to em@sedai.io.
