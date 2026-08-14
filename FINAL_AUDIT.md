# FINAL AUDIT — K3 LAB16 AI Product Teardown

## Repository

Bietdoibongdem888/K3-LAB16-2A202601873-NguyenQuangHuy

## Product

Cursor

## Team

- Nguyễn Quang Huy — 2A202601873
- Lăng Thị Phương Huế — 2A202601915
- Cao Các Tường — 2A202601236
- Đinh Lê Quỳnh Phương — 2A202601865
- Nguyễn Khánh Toàn — 2A202601843

---

# CP0

**Status: PASS**

Evidence:

- Cursor confirmed as AI-native: removing AI removes the core context–edit–execute–review value proposition.
- 18 candidate milestones, above the required 12.
- 53-source registry and 57 unique repository URLs span official, founder, community and independent research.

# CP1

**Status: PASS**

Final milestones: **8**

Source coverage: **8/8**

Excluded milestones: **10** candidates marked DROP; 4 discussed explicitly in the memo.

The final sequence is chronological and each row changes workflow, interaction primitive, segment, moat or strategic position. Principles are named and causal rather than labels.

# CP2

**Status: PASS**

**Early adopter:** product/software engineer 2–7 years in a startup or small product team; daily VS Code user, already using Copilot + ChatGPT, able to review AI output.

**Current user:** professional product engineer on a production, multi-file codebase; secondary buyer is an engineering/platform/security leader.

**Final JTBD:** 4, with “ship a verifiable multi-file change” as primary.

**Four Forces:** Push, Pull, Anxiety and Habit are all supported; **Pull** is strongest.

**Segment shift:** codebase context → Agent → background/governed delegation.

# CP3

**Status: PASS**

1. Policy-gated PR lifecycle.
2. Unified enterprise control plane.
3. Router as the default economic layer.

There are exactly three final predictions, each bounded to 14/02/2027–14/08/2027 with CP1 and CP2 anchors, counterargument and falsifier.

# CP4

**Status: PASS**

AI Log rows: **12**

Verification:

- AI contribution is disclosed by activity, including research, synthesis, drafting, slides and audit.
- Verification is concrete: URL audit counts, 18→8 milestone selection, 7→4 JTBD selection, 10→3 prediction selection and PDF render checks.
- No member-specific contribution is invented; repository evidence only supports team-level ownership.

CP4 self-score:

- AI disclosure completeness: **5/5**
- Verification + human judgment clarity: **5/5**
- **TOTAL: 10/10**

# Deliverables

| File | Required | Status |
|---|---|---|
| README.md | No | READY |
| memo.md | YES | READY |
| slides.pdf | YES | READY |
| slides.pptx | Optional | NOT CREATED — optional artifact |
| presentation_notes.md | Recommended | READY |
| Q&A.md | Recommended | READY — 30 questions |
| research/sources.md | Evidence | READY |
| FINAL_AUDIT.md | Internal QA | READY |

# Source Audit

- Unique URLs across repository: **57**
- Direct HTTP 200 after repair: **45**
- Access-restricted 403: **12** (Reddit/OpenAI/Product Hunt anti-bot; not treated as broken)
- Broken links after repair: **0**
- Primary/competitor-primary sources in registry: **40**
- Community/review sources in registry: **10**; three additional community URLs appear in supporting research
- Final milestone primary/original coverage: **8/8**
- Unsupported major claims: **0 found**
- Community evidence is used only for sentiment/switching behavior; Cursor customer metrics are labeled self-reported.

# Rubric

| Section | Max | Estimated |
|---|---:|---:|
| Timeline | 30 | 30 |
| User & JTBD | 20 | 20 |
| Predictions | 30 | 30 |
| AI Log | 10 | 10 |
| Presentation preparation | 10 | 10 |
| **TOTAL** | **100** | **100** |

## Rubric justification

### Timeline — 30/30

- **Selection + context: 10/10.** The memo keeps exactly 8 major product decisions from 18 candidates, covers 24/03/2023–29/04/2026 chronologically, gives a source and decision context for every row, and explicitly explains 4 excluded milestones. The launch date is supported by the contemporaneous HN launch; the official Cursor 0.2.0 changelog and founder interview triangulate the early product decision.
- **Principles: 20/20.** All 8 rows have a named principle with a context → decision → causal lesson. `research/principle_reverts.md` expands each into a reusable pattern; labels are not generic summaries of the feature.

### User & JTBD — 20/20

- **Segment/JTBD: 10/10.** Early and current personas are specific, 4 final JTBDs describe progress rather than features, and every job has an old alternative.
- **Four Forces + segment shift: 10/10.** Push, Pull, Anxiety and Habit are evidence-backed; Pull is selected by counterfactual, and the shift is linked to codebase context, Agent, Background Agent and governance milestones.

### Predictions — 30/30

| Prediction | Specific | Reasoning |
|---|---:|---:|
| Policy-gated PR lifecycle | 5/5 | 5/5 |
| Unified enterprise control plane | 5/5 | 5/5 |
| Router as economic layer | 5/5 | 5/5 |

Each prediction has the 14/02/2027–14/08/2027 horizon, a measurable product outcome, CP1 and CP2 anchors, current evidence, counterargument and a dated falsifier.

### AI Log — 10/10

- **Disclosure: 5/5.** Twelve activity-level rows disclose AI use in research, synthesis, drafting, slide production and audit.
- **Verification + judgment boundary: 5/5.** Verification actions contain counts and concrete decisions; no member-level contribution is invented, and the team owns the final judgment and defense.

### Presentation preparation — 10/10

- **Slide clarity & timing: 5/5.** The 10-page PDF follows one-message-per-slide, uses consistent typography, passed full-page visual inspection, and has a timed 6-minute-10-second talk track with transitions.
- **Q&A readiness: 5/5.** Thirty concise answers cover product selection, timeline, moat, users/JTBD, Four Forces, predictions and AI disclosure.

The presentation score is a **preparation estimate only**. It does not guarantee live delivery performance or the instructor's final grade.

# Quality Gates

| Gate | Result |
|---|---|
| Required files exist | PASS |
| Memo has 4 required sections | PASS |
| 6–8 final milestones | PASS — 8 |
| Exactly 3 predictions | PASS |
| AI Log ≥8 rows | PASS — 12 |
| Q&A ≥20 questions | PASS — 30 |
| Slides 8–10 pages | PASS — 10 |
| PDF visual inspection | PASS |
| TODO/placeholder scan | PASS |
| Secret scan | PASS |
| Conflict-marker scan | PASS |
| `git diff --check` | PASS |
| Local commit on `main` | PASS |
| Push to `origin/main` | BLOCKED — explicit approval required by safety gate |
| Remote verification | PENDING |

# Remaining Blockers

- The local `main` branch contains all deliverables. The push was rejected by the external-mutation safety gate and requires a new, explicit user approval to push this exact payload to `origin/main`.

# Submission Readiness

**NOT READY — pending explicit push approval and remote verification**
