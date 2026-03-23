# LTI-CFGP — Generation Plan

This file tracks the incremental generation of `LTI-CFGP.md` to work around context
limits. Each artifact is generated in a separate Copilot session and appended to the
final document.

---

## Output File

`LTI-CFGP/LTI-CFGP.md`

---

## Artifact Checklist

| #   | Artifact                                                 | Status     | Notes |
| --- | -------------------------------------------------------- | ---------- | ----- |
| 1   | LTI Software Description                                 | ⬜ Pending |       |
| 2   | Main Functions                                           | ⬜ Pending |       |
| 3   | Lean Canvas (Markdown table)                             | ⬜ Pending |       |
| 4   | 3 Main Use Cases + Mermaid flowcharts                    | ⬜ Pending |       |
| 5   | Data Model + Mermaid erDiagram                           | ⬜ Pending |       |
| 6   | High-Level System Design + Mermaid graph                 | ⬜ Pending |       |
| 7   | C4 Component Diagram (Notification & Scheduling Service) | ⬜ Pending |       |

**Status legend:** ⬜ Pending · 🔄 In Progress · ✅ Done · ❌ Blocked

---

## Instructions for Each Session

1. Open a **new Copilot chat**.
2. Paste the **master prompt** (from `prompts.md`) followed by:
   > "Generate ONLY Artifact N — [Artifact Name]. Output raw Markdown only,
   > starting directly with the `##` heading for that artifact."
3. Copy the output and **append** it to `LTI-CFGP.md`.
4. Update the status in the table above.
5. Repeat for the next artifact.

---

## Fallback Instructions

- **Mermaid C4 not rendering?** Ask Copilot to rewrite Artifact 7 using
  `graph TD` with C4-style labels.
- **erDiagram too large?** Split Artifact 5 into two messages:
  entity definitions first, then relationships.
- **flowchart TD ambiguous?** Ask Copilot to use `subgraph` blocks to
  separate actor swimlanes.

---

## Session Log

| Date | Artifact | Model Used | Issues |
| ---- | -------- | ---------- | ------ |
|      |          |            |        |
