# SAT Drill Room

Static SAT drill site served by GitHub Pages. Progress (attempts, review schedule, miss reasons) is stored in each browser's localStorage, so it is per device.

## Adding questions

1. Add a JSON file to `questions/` containing an array of questions.
2. List the file in `questions/index.json`.

Question format:

```json
{
  "id": "tsp-001",
  "type": "Text Structure and Purpose",
  "sub": "sentence function",
  "passage": "Text. [[Underlined sentence.]] *Italic title.*\n- bullet note\n- bullet note",
  "table": { "title": "Optional", "cols": ["A", "B"], "rows": [["1", "2"]] },
  "prompt": "Which choice best states the function of the underlined sentence?",
  "choices": ["...", "...", "...", "..."],
  "answer": "A",
  "expl": "Why the answer is right and why the trap is wrong."
}
```

- `id` must be unique across all files and never reused (progress is keyed on it).
- `type` should be one of the official R&W skill names: Words in Context, Text Structure and Purpose, Cross-Text Connections, Central Ideas and Details, Command of Evidence, Inferences, Boundaries, Form, Structure, and Sense, Transitions, Rhetorical Synthesis. Other values work and sort after these.
- `sub`, `passage`, `table`, `expl` are optional.

## Review schedule

A missed question comes back 1 day later. Each correct answer on a due review pushes it to 3 days, then 7 days, then retires it. Missing it again resets it to 1 day.
