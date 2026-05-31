# Relationship Chat Analysis Skill

Evidence-based analysis of long, noisy relationship chat histories. This skill cleans message exports, segments the relationship timeline, extracts interaction patterns from both participants, and synthesizes repeated emotional and communication dynamics.

## Usage

```text
/relationship-chat-analysis
/relationship-chat-analysis --dry-run
/relationship-chat-analysis --period 2026-01 2026-03
/relationship-chat-analysis --focus "conflict repair and mixed signals"
```

## What It Does

1. Discovers chat logs or uses user-provided files.
2. Normalizes messages into a structured timeline.
3. Removes or labels low-signal noise such as stickers, media placeholders, system messages, deleted messages, duplicated exports, and unrelated content.
4. Segments the chat into relationship episodes such as ordinary contact, conflict, distance, repair, intimacy, planning, and breakup/reconciliation.
5. Extracts evidence-based relationship dimensions from each episode.
6. Synthesizes recurring patterns across time.
7. Produces a report that separates observations, interpretations, uncertainties, and safety concerns.

## Analysis Dimensions

| Dimension | What it captures |
|-----------|------------------|
| Initiation and pursuit | Who starts contact and who sustains it |
| Responsiveness | Reply timing, silence, coldness, and availability |
| Emotional bids | Requests for care, reassurance, closeness, attention, or repair |
| Validation and invalidation | Whether feelings are acknowledged, minimized, mocked, or redirected |
| Conflict escalation | How disagreement intensifies |
| Repair attempts | Apologies, softening, accountability, humor, reassurance, reconnection |
| Avoidance and deflection | Topic shifting, withdrawal, stonewalling, ambiguity |
| Boundaries and pressure | Consent, respect, control, guilt, demands, repeated pushing |
| Effort balance | Who explains, waits, plans, accommodates, or follows up |
| Intimacy signals | Trust, vulnerability, affection, future orientation |
| Ambiguity and mixed signals | Contradictory closeness/distance or promise/withdrawal loops |
| Safety concerns | Threats, coercion, stalking, self-harm, harassment, sexual pressure |

## Output Sections

1. Relationship Timeline
2. Data Quality and Missing Context
3. Communication Pattern
4. Emotional Needs and Bids
5. Conflict Escalation Pattern
6. Repair and Reconnection Pattern
7. Distance, Avoidance, and Coldness
8. Boundaries, Pressure, and Safety
9. Effort Balance and Power Dynamics
10. Repeating Loops
11. Blind Spots for Each Person
12. What the Evidence Does Not Support

## Output Files

- **Analysis**: `relationship-analysis/YYYYMMDD-relationship-chat-analysis.md`
- **Corpus manifest**: `relationship-analysis/YYYYMMDD-chat-corpus-manifest.json`

## Requirements

- Chat logs in text-like form, or pasted conversation text
- Enough dates or ordering information to infer a timeline
- Speaker names or aliases when possible
- Optional user context about the relationship and the question they want answered

## Notes

This skill does not diagnose either participant. It can identify evidence of patterns, risk signals, and plausible interpretations, but it should state uncertainty clearly and avoid claiming private motives as fact.
