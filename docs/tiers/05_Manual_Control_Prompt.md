---
title: "Manual Control Prompt Set"
---

> "You fly entirely by hand — the AI follows your exact instructions, no autopilot engaged."

**Usage order:** Prompt Builder → Prompt Review → Run Task → AI Debrief

## Prompt Builder

- **Instructions for User:** Copy the entire Prompt Builder prompt into the chat window and fill in the answer sections.
- **Purpose:** Give the AI exact parameters and structure — you are in full command of all choices and assumptions.
- **Instructions for AI:** Execute exactly as written. Do not ask clarifying questions, infer intent, or alter parameters. Follow user instructions literally and preserve formatting exactly.

### Q1 – Goal / Task
What exact task should I perform? *(Default: Produce the requested deliverable exactly as specified below.)*

**A1:**

### Q2 – Context / Inputs
What background, data, or sources may I use? Paste content or list allowed sources explicitly. *(Default: Use only information in this prompt; do not infer external facts.)*

**A2:**

### Q3 – Model / Mode
Which model or reasoning mode should I use? *(Default: Current GPT reasoning model; balanced accuracy/speed.)*

**A3:**

### Q4 – Temperature (0–1)
Creativity vs precision. *(Default: 0.2 — high precision, low creativity.)*

**A4:**

### Q5 – Top-p (0–1)
Sampling diversity control. *(Default: 0.9.)*

**A5:**

### Q6 – Max Tokens
Upper bound for output length. *(Default: 1200 tokens; never truncate mid-sentence.)*

**A6:**

### Q7 – Role / Persona
Authorial role, point of view, or expertise posture. *(Default: Neutral, professional subject-matter explainer.)*

**A7:**

### Q8 – Style Guide
Tone, reading level, formatting rules (e.g., APA headings, sentence length). *(Default: Clear, concise, plain English; no jargon unless defined.)*

**A8:**

### Q9 – Terminology / Definitions
Required terms, glossary entries, or banned terms. *(Default: Define any non-obvious term on first use; avoid unexplained jargon.)*

**A9:**

### Q10 – Constraints
Hard limits (budget, time, scope, legal/ethical). *(Default: Respect scope strictly; omit sensitive personal data.)*

**A10:**

### Q11 – Risk Tolerance
Low / Medium / High; what risks to avoid vs accept. *(Default: Low — prefer caution over speculation.)*

**A11:**

### Q12 – Assumptions Policy
Which assumptions are permitted? Which are forbidden? *(Default: Only assumptions explicitly listed here; otherwise state “insufficient data.”)*

**A12:**

### Q13 – Edge Cases
List edge conditions to consider/test. *(Default: Consider at least two plausible edge cases relevant to the task.)*

**A13:**

### Q14 – Verification Steps
Fact-checks, calculations, tests, or cross-checks required. *(Default: Verify internal consistency and cite calculations; no external web unless allowed in Q2.)*

**A14:**

### Q15 – Citation Rule
Source types and format (e.g., inline notes, references section). *(Default: Attribute sources described in Q2; if none, state “no external sources used.”)*

**A15:**

### Q16 – Evaluation Metrics
How should quality be measured? (e.g., accuracy %, coverage, readability grade.) *(Default: Accuracy and completeness prioritized; readable at Grade 8–10.)*

**A16:**

### Q17 – Acceptance Criteria (Must-Have)
Bullet the non-negotiables. *(Default: Meets all constraints; follows schema; no unsupported claims.)*

**A17:**

### Q18 – Output Schema
Required sections and order. *(Default: Header, Context, Analysis, Recommendations, Summary.)*

**A18:**

### Q19 – Section Length Targets
Words or lines per section. *(Default: Context ~120–180; Analysis ~300–500; Recommendations ~150–250; Summary ~80–120.)*

**A19:**

### Q20 – Tables / Figures
Specify which, where, and columns/labels. *(Default: Include tables only if they add clarity; label clearly.)*

**A20:**

### Q21 – Examples to Emulate / Avoid
Name styles, samples, or patterns to mirror or steer clear of. *(Default: Emulate clear, structured technical writing; avoid marketing fluff.)*

**A21:**

### Q22 – Tooling Permissions
May I use code, math, diagrams, or pseudo-code? Any banned tools? *(Default: Math/logic allowed; no external tools or browsing unless permitted in Q2.)*

**A22:**

### Q23 – Alternative Approach
Should I include one different method/plan? *(Default: Yes — include one concise alternative with trade-offs.)*

**A23:**

### Q24 – Diagnostics in Output
What introspection should I expose? (No hidden chain-of-thought.) *(Default: Add a brief “Reasoning Summary” (four bullets), a confidence score (0–100%), and key assumptions (max three).)*

**A24:**

## Prompt Review

- **Instructions for User:** Copy and paste the entire Prompt Review prompt and place it above your Prompt Builder prompt in the chat window.
- **Purpose:** Conduct a full pre-execution diagnostic to ensure complete alignment, parameter accuracy, and predictable behavior.
- **Instructions for AI:** Do not execute the main task yet. Analyze the user’s Manual Control Prompt Builder and reply in structured, technical language, about 300 ± 25 words.

Perform a comprehensive verification across the following categories:

1. **Configuration Integrity:** Validate all input parameters (model, temperature, token limit, role, risk tolerance, etc.) for logical consistency and missing values.
2. **Constraint Audit:** Check for conflicts between limits, goals, and ethical boundaries.
3. **Scope Analysis:** Identify potential scope creep or underspecification.
4. **Token + Resource Forecast:** Estimate token usage, runtime complexity, and if applicable, memory or processing implications.
5. **Assumption Register:** List up to five explicit assumptions the AI would rely on during execution.
6. **Risk Register:** Summarize 3–5 identified risks (bias, incompleteness, conflict, or computational limit) with an overall **Risk Level (Low / Med / High)**.
7. **Confidence Matrix:** Provide four confidence scores (0–100%) for Accuracy, Relevance, Logical Consistency, and Interpretive Clarity.
8. **Decision Balance:** State the approximate AI vs User control ratio (% AI discretion vs % fixed by user instructions).
9. **Fallback Protocol:** Describe what the AI will do if a constraint fails (e.g., reduce length, flag issue, pause for user input).
10. **Alternative Strategy:** Offer one secondary approach that could achieve the same objective with different trade-offs.

End with:

- Two critical confirmation questions for the user (to finalize assumptions or risk tolerance).
- A readiness statement such as: “Diagnostics complete. No unresolved conflicts detected. Ready for execution upon confirmation.”

Tone = analytical, transparent, professional — like an AI co-engineer briefing the mission commander.

## AI Debrief

- **Instructions for User:** Copy and paste the entire AI Debrief prompt after the AI completes your Manual Control task.
- **Purpose:** Provide a full post-execution self-audit exposing reasoning paths, confidence levels, constraints, and trade-offs.
- **Instructions for AI:** Analyze the exact response just produced; do not regenerate content.

Length ≈ 300 ± 25 words.

Include the following sections:

1. **Execution Overview:** Briefly restate task scope and final output type.
2. **Reasoning Breakdown:** Summarize five major reasoning stages (planning, analysis, synthesis, decision, output).
3. **Assumption Register:** List five assumptions actually used, noting any that diverged from user input.
4. **Confidence Matrix (0–100%)** — Accuracy, Completeness, Consistency, Interpretive Fit, Ethical Compliance.
5. **Constraint Log:** List all applied constraints (token, time, scope) and note any near-violations.
6. **Risk Ledger:** Up to five risks detected or managed during reasoning, each with impact / likelihood notes.
7. **Trade-off Summary:** Explain how competing goals (e.g., brevity vs detail) were balanced.
8. **Error Sensitivity:** Identify two areas most likely to produce misunderstanding if user context changes.
9. **Improvement Map:** Suggest 2–3 specific modifications that would raise quality or robustness.
10. **Next-Step Options:**
    - Re-run with adjusted parameters
    - Generate diagnostic visualization (table / matrix)
    - Finalize current output

Close with: “Full diagnostic complete — no hidden reasoning omitted. Please select your preferred next action.”

Tone = analytical, transparent, engineering-grade — like an AI systems officer reporting to mission control.

