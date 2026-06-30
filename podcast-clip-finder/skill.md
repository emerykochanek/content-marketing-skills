---
name: podcast-clip-finder
description: Identify the best short-form clips from a podcast transcript for LinkedIn and YouTube Shorts/Reels. Shows exact timestamps, what to cut for conciseness, and platform-specific hooks. Optimized for 1 IDEA podcast — engineering-leader and senior practitioner audiences. Use when the user provides a transcript and wants shareable clips.
---

# Podcast Clip Finder

## Goal
Given a transcript (with or without timestamps), identify the 3–6 best clips for short-form video. For each clip, output:
- Where it starts and ends (timestamps or speaker cues if no timestamps)
- A concise edit — what to cut to get it under 60s
- A LinkedIn hook (caption + opening line)
- A YouTube hook (title for a Short/Reel)

Do not fabricate quotes. Ground every clip in actual language from the transcript.

## The Audience
Engineering leaders and senior practitioners: Staff and Principal Engineers, CTOs, VPs of Engineering, DevOps, SRE, Platform, Cloud, FinOps, infrastructure. They are skeptical of hype and respond to specificity. They skip anything that sounds like a keynote intro or vendor positioning.

## What Makes a Clip Worth Clipping

A clip lands when it contains one of:
- A concrete failure mode or hard-won lesson
- A counter-intuitive claim that a practitioner would argue with or share
- A sharp definition of something that's usually left vague
- A moment where the speaker names a tradeoff and commits to a side
- A decision the guest made that cost something
- A pattern engineers recognize from their own work

A clip does NOT land when it contains:
- Abstract framing with no payoff ("the future of AI is...")
- Motivational statements without evidence
- Episode context that only makes sense if you listened to the whole thing
- Long setups with the punchline cut off

## Working Process

### 1. Read the Full Transcript
Before flagging any clip, identify:
- The 3–4 recurring ideas in the episode
- The sharpest single claim (the most quotable sentence)
- The moments where the speaker's language gets specific — numbers, names, decisions, failures

### 2. Score Each Candidate Clip on Three Dimensions

**Standalone-ness (1–3):** Can someone understand it without having heard anything else?
- 1 = requires too much context
- 2 = marginal, could work with a tight intro
- 3 = fully self-contained

**Hook strength (1–3):** Does the first sentence make you want to keep watching?
- 1 = flat opener, builds slowly
- 2 = decent but not urgent
- 3 = immediately interesting — names a problem or makes a claim

**Specificity (1–3):** Does it use concrete language or generic language?
- 1 = mostly generic
- 2 = some specifics
- 3 = numbers, examples, names, or a precise claim

Select clips with total score ≥ 7. Include at least one clip per scoring tier (short ≤30s, medium 31–60s).

### 3. Draft the Edit
For each clip, specify:
- **Keep:** the core exchange or statement
- **Cut:** filler, false starts, lengthy setup, tangents that break standalone-ness
- **Target runtime:** under 60s is ideal; under 90s is acceptable if the payoff is strong

Be surgical. Do not recommend cutting a setup that the punchline depends on.

**Assembled clips are allowed.** If no single clean clip exists but the best material is spread across the transcript, you may propose assembling non-contiguous lines into a single clip — reordering or combining quotes from different timestamps — as long as:
- Every line is quoted exactly as spoken (no paraphrasing)
- The assembled clip does not change the meaning of what anyone said
- The resulting exchange would read as natural to a listener who hasn't heard the full episode
- Nothing is put in a speaker's mouth that they didn't say

When proposing an assembled clip, list each piece with its timestamp so the editor knows exactly where to pull from. Flag it clearly as an assembled clip in the output.

### 4. Write Platform Hooks

#### LinkedIn Hook
LinkedIn clips play without audio by default. The caption is the hook.

Structure:
```
[Single provocative sentence — the claim or failure in plain language]

[1–2 sentences of tension or stakes]

[Optional: short setup for the clip itself if context is needed]

Full episode: [leave blank — user fills in link]
```

Rules:
- First sentence must work as a standalone statement, not a teaser
- Do not use "In this clip..." or "Check out this video..."
- Do not use em-dashes as a crutch
- Avoid "game-changer," "unlock," "reimagine," "transform"
- Engineering audiences share posts that say something true, not posts that promise revelation

Good LinkedIn opener examples:
- Most AI failures are data failures, not model failures.
- Your agents won't save you if your on-call process is broken.
- The hardest part of AI in production isn't the model — it's the eval.
- We shipped a feature that reduced costs 40%. Nobody wanted to maintain it.

#### YouTube Short / Reel Title
Short, punchy, specific. 5–9 words max.

Rules:
- Must work without seeing the clip first
- Name the problem or the lesson — not the episode
- No clickbait questions unless the episode genuinely answers them

Good examples:
- Why AI Agents Break at Scale
- The Mistake Every Platform Team Makes
- AI Can't Fix a Broken On-Call Process
- What 40% Cost Reduction Actually Costs
- When to Stop Using Kubernetes

Weak examples:
- This Will Change How You Think About AI
- The Most Important Lesson I Learned
- You're Doing It Wrong

## Output Format

For each clip, output:

---
### Clip [N] — [2–4 word label, e.g. "The Data Problem"]

**Score:** [standalone / hook / specificity] = [total]

**Find it:**
> "[Opening words of the clip...]" → "[Closing words of the clip...]"
> Approx. [timestamp or page/paragraph reference if no timestamps]

**Runtime as-is:** ~[estimate]s

**Edit to [target]s:**
- Cut: [specific lines, tangents, or phrases to remove]
- Keep: [the core — starting with what line, ending with what line]

**LinkedIn caption:**
[Full caption, ready to paste]

**YouTube Short title:**
[Title]

---

Repeat for each clip. After all clips, add a section:

## Best Single Clip
Recommend which one clip to post first if the user has bandwidth for only one. State the reason in one sentence.

## Clip Variety Check
Note whether the set covers multiple angles (e.g., failure story, sharp definition, counter-intuitive claim). If three clips say the same thing in different ways, flag it.

## Style Rules

- Quote the transcript accurately. Do not paraphrase into something sharper than what was said.
- If you recommend a cut, explain why in one phrase — do not over-justify.
- Platform hooks should sound like the guest's voice, not a marketer's voice.
- Short-form content for this audience rewards specificity over energy. A calm, specific claim beats an enthusiastic vague one.
- Avoid hooks that promise "the real truth" or "what they don't tell you" — that pattern signals low-quality content to this audience.
