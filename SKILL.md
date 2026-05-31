---
name: thinking-patterns
description: Use this skill whenever the user wants longitudinal cognitive pattern analysis from recorded conversation transcripts, Fathom notes, coaching calls, meeting transcripts, or multi-session self-reflection data. This skill extracts evidence-backed thinking patterns across months of conversations, including cognitive distortions, metaphors, hedging, code-switching, decision heuristics, avoidance, agency language, competing commitments, role shifts, energy signals, contradictions, and blind spots. Trigger it even when the user casually asks to analyze "how I think", "patterns in my calls", "blind spots from transcripts", or similar multi-session transcript analysis.
---

# Thinking Patterns

Analyze months of recorded conversation transcripts to identify recurring cognitive patterns, contradictions, and blind spots. The output is a single evidence-grounded analysis document with dated quotes and a short "things you do not see" summary.

## When To Use

Use this skill for tasks involving:

- Fathom or meeting transcripts across multiple dates
- Coaching, client, podcast, workshop, lab, or impromptu conversation corpora
- Longitudinal analysis of how one person frames problems, makes decisions, avoids topics, or shifts roles
- Detection of blind spots, competing commitments, contradictions, and execution gaps
- Bilingual transcript analysis where Russian and English may both appear

Do not use this skill for a single ordinary meeting summary. If the user only needs one transcript summarized, use normal summarization unless they explicitly ask for cognitive patterns or blind spots.

## Inputs

Expected transcript files:

- Markdown files named with a leading date, such as `YYYYMMDD-*.md`
- Fathom transcript content with identifiable speaker lines
- Optional reference documents describing current priorities, profile, or strategic decisions

Configuration lives in `config.json`. If the configured paths or reference documents do not match the user's workspace, adapt them before running analysis rather than assuming the original author-specific paths are valid.

## Workflow

1. Read `config.json`.
2. Read `references/instructions.md` for the full orchestration procedure.
3. Use `references/extraction-prompt.md` for per-transcript extraction.
4. Use `references/synthesis-prompt.md` for cross-session synthesis.
5. Use `references/blindspot-prompt.md` for contradiction and blind spot detection.
6. Produce the final analysis in the configured output folder.

## Core Behavior

- Ground every substantive finding in evidence from at least two sessions when possible.
- Preserve original-language quotes. Add translations when needed for readability.
- Separate observed evidence from interpretation.
- Treat unidentified speakers conservatively and mark uncertainty when attribution is ambiguous.
- Prefer dated, specific quotes over broad impressions.
- Keep the analysis non-destructive: create a new output file and only append links when the target note exists or can be safely created.

## Output

Default output:

- Analysis document: `ai-research/YYYYMMDD-thinking-patterns-analysis.md`
- Optional daily note link under `## Research`

The final document should include the ten configured analysis sections plus a concise summary of the five most important blind spots or unseen patterns.

## Bundled References

- `references/instructions.md`: detailed implementation guide
- `references/extraction-prompt.md`: 12-dimension per-transcript extraction prompt
- `references/synthesis-prompt.md`: cross-session synthesis prompt
- `references/blindspot-prompt.md`: contradiction and blind spot prompt
