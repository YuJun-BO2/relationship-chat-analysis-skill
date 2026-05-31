---
name: relationship-chat-analysis
description: Use this skill whenever the user wants evidence-based relationship or romantic communication analysis from long chat histories, messy message exports, screenshots transcribed to text, LINE, WhatsApp, Telegram, iMessage, Messenger, Discord, or similar interpersonal conversation records. This skill cleans noisy chat logs, segments the relationship timeline, analyzes both people's communication patterns, conflict cycles, emotional bids, repair attempts, avoidance, boundaries, effort balance, intimacy signals, and blind spots. Trigger it for requests about "analyze our chats", "is this relationship pattern healthy", "why do we keep fighting", "what does this conversation reveal", "relationship blind spots", "attachment signals", "coldness", "mixed signals", breakups, ambiguous dating, reconciliation, or long emotional chat analysis.
---

# Relationship Chat Analysis

Analyze long, noisy relationship chat histories to identify interaction patterns, emotional dynamics, conflict cycles, repair attempts, effort balance, and blind spots. The output is an evidence-grounded report that distinguishes observable facts from cautious interpretation.

## When To Use

Use this skill for:

- Long romantic, dating, breakup, reconciliation, or ambiguous relationship chat histories
- LINE, WhatsApp, Telegram, iMessage, Messenger, Discord, Instagram DM, SMS, or exported text logs
- Messy chat records containing system messages, media placeholders, stickers, duplicated content, deleted messages, or unrelated material
- Requests to understand patterns across weeks or months, not just summarize one exchange
- Analysis of conflict escalation, coldness, distance, mixed signals, emotional needs, repair attempts, boundaries, control, validation, invalidation, or effort imbalance

Do not use this skill for ordinary sentiment classification of short text, legal conclusions, clinical diagnosis, or deciding whether someone "definitely" has a disorder. If the chat contains threats, coercion, stalking, physical danger, self-harm, or sexual pressure, flag the safety concern and keep the analysis grounded in the text.

## Inputs

Expected inputs can include:

- One or more exported chat files
- Manually pasted chat logs
- Screenshots that have already been transcribed into text
- Optional context from the user, such as relationship status, date range, participant names, or what question they want answered

If the export format is unknown, infer the structure conservatively and ask for clarification only when speaker/date attribution would be too unreliable.

## Workflow

1. Read `config.json`.
2. Read `references/instructions.md` for the full orchestration procedure.
3. Use `references/cleaning-prompt.md` to normalize and filter noisy chat records.
4. Use `references/extraction-prompt.md` for episode-level relationship pattern extraction.
5. Use `references/synthesis-prompt.md` for cross-episode relationship synthesis.
6. Use `references/blindspot-prompt.md` for blind spots, unsupported claims, and safety concerns.
7. Produce the final report in the configured output folder.

## Core Behavior

- Preserve both participants' messages. Do not reduce the analysis to only one person's perspective.
- Ground every major claim in dated examples or message quotes when available.
- Separate `observation`, `interpretation`, and `uncertainty`.
- Avoid diagnosis, mind-reading, moral verdicts, or manipulative certainty.
- Treat missing context as missing context. Do not fill gaps with a story that the messages do not support.
- Identify patterns across repeated episodes rather than over-weighting one heated message.
- Keep original-language quotes when useful and translate only for clarity.
- Protect privacy: do not expose unnecessary third-party names, phone numbers, addresses, or sensitive identifiers in the final report.

## Output

Default output:

- Analysis document: `relationship-analysis/YYYYMMDD-relationship-chat-analysis.md`
- Optional cleaned corpus manifest: `relationship-analysis/YYYYMMDD-chat-corpus-manifest.json`

The final report should include a timeline, communication pattern analysis, conflict and repair cycles, emotional needs, effort balance, blind spots for each side, safety concerns if present, and a section listing what the evidence does not support.

## Bundled References

- `references/instructions.md`: detailed implementation guide
- `references/cleaning-prompt.md`: chat normalization and noise filtering
- `references/extraction-prompt.md`: episode-level relationship pattern extraction
- `references/synthesis-prompt.md`: cross-episode synthesis
- `references/blindspot-prompt.md`: blind spots, unsupported claims, and safety review
