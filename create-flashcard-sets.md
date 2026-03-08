X = _

We will build a flashcard deck about [X] as a structured artifact, one topic at a time.

---

## Structure

The artifact is a tree using decimal outline numbering (e.g. 1, 1.1, 1.1.1, …). Every node is one of two types:

- **TOPIC** — an organizational node. Its children are either all TOPICs or all CARDs, never mixed.
- **CARD** — a leaf node. Has a Front (question) and Back (answer).

CARDs under a TOPIC should collectively cover the semantic space of that TOPIC.

---

## Workflow

1. Propose 5–8 top-level TOPICs for [X]. Ask me to confirm, reorder, add, or remove before continuing.
2. Once I confirm, begin with TOPIC 1. If it needs sub-TOPICs, propose them and ask me to confirm. If it can be covered directly by CARDs, generate 5–10 CARDs.
3. Maintain a single artifact containing the full deck so far. Update it each round — never output cards outside the artifact.
4. After each batch, ask: "More for this topic, or continue to the next?"
   - **more** → generate additional CARDs for the same TOPIC, continuing the numbering.
   - **continue** → move to the next TOPIC.
   - **[specific topic name or number]** → jump to that TOPIC.
5. Repeat until I say we are done.

At any point I may:
- Ask you to split a TOPIC into sub-TOPICs (converting its CARDs into a deeper level).
- Ask you to add, edit, or delete individual CARDs or TOPICs.
- Say **export** → output an Anki-importable tab-separated block (see Export below).

Always update the artifact to reflect any changes.

---

## Card Quality Rules

A CARD has a **Front** (question) and a **Back** (answer).

### Requirements

- **Atomic:** Front tests exactly one fact, distinction, mapping, role, or mechanism.
- **Clear:** Front has one unambiguous answer.
- **Least-context:** Front provides the minimum context needed while still being unambiguous.
- **Recall-based:** Answerable from memory, not recognition.
- **Compact:** Back is short — usually a couple words, only rarely one short sentence.
- **Meaningful:** Worth remembering.

### Prefer

- Distinctions
- Roles
- Mappings
- Cause/effect

### Avoid

- Broad "What is X?" cards
- Paragraph-length backs
- Multi-part answers
- Cards that list several properties at once
- Vague or subjective wording
- Binary questions: true/false, either/or, this or that
- If a concept is too broad, split it into multiple cards.
- Do not include explanations.

### Self-Check

Before outputting, check every card against: atomic, clear, least-context, recall-based, compact, meaningful. Rewrite any card that fails.

---

## Artifact Format

The artifact is a numbered outline. TOPICs show their label. CARDs show Front/Back.

```
1 [TOPIC] First Top-Level Topic
  1.1 [TOPIC] A Subtopic
    1.1.1 [CARD]
    Front: ...
    Back: ...
    1.1.2 [CARD]
    Front: ...
    Back: ...
  1.2 [TOPIC] Another Subtopic
    1.2.1 [CARD]
    Front: ...
    Back: ...
2 [TOPIC] Second Top-Level Topic
  2.1 [CARD]
  Front: ...
  Back: ...
  2.2 [CARD]
  Front: ...
  Back: ...
```

---

## Export (on request)

When I say **export**, output a tab-separated block suitable for Anki import. One card per line: `Front\tBack\tTags`. Tags should be the TOPIC path with `::` separators (Anki hierarchical tag format).

Example:

```
What distinguishes X from Y?	Z	X::First_Topic::Subtopic
```
