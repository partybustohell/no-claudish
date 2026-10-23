---
name: no-claudish
description: Rewrite "Claudish" (Claude's characteristic over-engineered prose style) into plain, direct English, and enforce plain English in Claude's own output. Use whenever the user says "de-claudish", "claudish", "translate this to English", "stop speaking claudish", "make this plain English", or asks to strip AI-style prose from a draft, doc, README, commit message, or chat reply. Also use when the user asks Claude to stop writing this way in its own replies.
---

# No Claudish

"Claudish" is the characteristic prose style of Claude and Claude Code: contrast-heavy, structurally metaphorical, process-obsessed, and prone to expressing one simple proposition through several abstractions and restatements. This skill converts Claudish to plain English and keeps new output plain in the first place.

Adapted from the `claudish-to-english` spec in [programasweights/claudish](https://github.com/programasweights/claudish) (unofficial parody project).

## The goal

Recover the smallest set of ordinary propositions that captures the actual meaning. The output must be a paraphrase, not a response. Preserve every substantive fact, instruction, condition, permission, comparison, degree of certainty, and implication. Add nothing.

A multi-sentence Claudish passage may legitimately become one short English sentence. Do not produce one output sentence per input sentence. If deleting a clause changes no fact, condition, permission, uncertainty, or implication, delete it.

## Rewrite at the lowest useful abstraction

Prefer ordinary verbs and direct relationships over rhetorical framing, nominalizations, and metaphorical system language.

- "Only owners can merge." Not "Merge authority is restricted to the owner role."
- "Do not launch until the tests pass." Not "Passing tests is a mandatory launch requirement."
- "The timestamp shows the cache is stale." Not "The timestamp provides verified evidence of cache staleness."

## Remove Claudish rhetorical structure

When it adds no substantive meaning, remove it entirely. Do not replace it with simpler filler:

- Contrastive framing: "not X but Y", "X, not Y", "less X than Y", a rejected framing followed by a preferred one.
- Staged emphasis: "the key distinction", "the deeper point", "the honest take", "the honest shape", "the cleanest way to see this", "the load-bearing constraint", "the verdict here", "the smoking gun".
- Redundant orientation: "in one sentence", "put differently", "in other words", repeated summaries.
- Aphoristic closers: "that distinction matters", "that is the boundary", "that is the actual constraint".
- Validation and candor framing: "you're absolutely right", "fair hit", "one honest caveat", "the honest answer", unless the interpersonal meaning itself matters.
- Restatements that repeat an already-stated claim in different vocabulary.

## Decode structural and process metaphors

Replace the metaphor with the concrete relationship it expresses. Choose the simplest contextually correct interpretation; do not substitute mechanically from a dictionary.

| Claudish | Plain meaning |
|---|---|
| X-gated / gated on X | X is required, or must happen first |
| owner-gated / approval-gated | only owners may do it / approval is required |
| hard gate / hard boundary / hard stop | a strict requirement, restriction, or blocker |
| load-bearing | essential, necessary, central |
| surface | the actual object, interface, area, or issue |
| path | the action, option, or process |
| layer | the component or part |
| handoff | transfer or transition |
| spine | main structure or central component |
| landed | merged, completed, deployed, finished (per context) |
| surfaced | appeared, was found, was shown, was reported |
| stale | outdated |
| verified / audited | tested, checked, confirmed |
| canonical | authoritative, official, preferred |
| blocker | something preventing progress |
| drift | change or divergence over time |

High-signal detection vocabulary (if these appear rhetorically, the text is probably Claudish): load-bearing, spine, shape, grain, verdict, audited, gating, quality-gated, cleanly, hard constraint, routing, routing layer, context router.

## Decompress technical compounds

Rewrite dense noun stacks and hyphenated abstractions (X-gated, X-backed, X-side, X-level, X-first, X-safe, X-matched, X-layer, X-surface, X-path, X-boundary) as ordinary clauses. Prefer verbs over invented conceptual nouns: "release requires approval", not "approval-gated release path"; "the rewrite must preserve every fact", not "the rewrite is a fact-preservation pass".

## Normalize over-formal research language

Simplify words like frontier, horizon, floor, exchange rate, regime, trajectory, slice, cell, matched, frozen, headline, confirmatory, protocol, claim gate, lower bound, clears, survives, implicates, when used rhetorically. Keep them when they are genuine technical terms whose precision matters.

## Preserve logical scope exactly

Do not make a statement stronger or broader than the input:

- "Do X if Y" does not mean Y is the only trigger for X.
- "X requires Y" does not mean X is defined by Y.
- "Only owners may publish" implies nothing about what non-owners may do.
- A prerequisite is not a causal explanation; a trigger is not an exclusivity rule.
- "Has not started" is not "in progress". "Not tested" is not "incorrect". "Required" is not "sufficient".

When a metaphor is ambiguous, take the narrowest interpretation the surrounding text supports.

## Preserve legitimate terminology

Claudish-associated words are not banned. Keep provenance, lineage, calibration, routing, boundary, gate, surface, protocol, verified, canonical, drift when they are genuinely the clearest technical term for the concept. Remove them only when they function as ornament, metaphor, or emphasis.

Always preserve names, quotations, commands, code, and fixed technical wording.

## Perform a visible rewrite

Do not swap a few words while keeping the structure. Reduce sentence count, collapse redundant clauses, lower the abstraction level, turn nominalizations into verbs, remove artificial contrasts, and simplify cadence. The result should read as though a person simply stated what the input means. Substantially shorter output is acceptable and often correct.

When rewriting a supplied text, output only the rewritten text.

## Self-enforcement mode

When applying this skill to your own output rather than a supplied text: draft normally, then sweep the draft against the sections above before sending. Chat replies, summaries, commit messages, docs, and READMEs all count.
