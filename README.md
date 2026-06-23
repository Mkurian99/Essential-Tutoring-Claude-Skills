[README (1).md](https://github.com/user-attachments/files/29266053/README.1.md)
# Tutor Skills Suite

A complete set of 12 Claude skills designed for general subjects and executive functioning tutors. Each skill targets a simple, repeated tutoring task — usable in under 5 minutes during a live session.

---

## The 12 Skills

| # | Skill | What It Does | When to Use |
|---|-------|-------------|-------------|
| 1 | [`smart-goals-planner`](./smart-goals-planner/SKILL.md) | SMART goal-setting across 5 life domains (Academic, Recreation, Physical, Service, Personal) with progress tracking | Start of engagement, semester kickoff, monthly goal review |
| 2 | [`session-agenda-builder`](./session-agenda-builder/SKILL.md) | Build focused, time-boxed session agendas from student context | Before every session; 30/45/60-min templates |
| 3 | [`session-notes-writer`](./session-notes-writer/SKILL.md) | Write post-session notes (Quick Notes + Parent Summary formats) | After every session; dual-audience output |
| 4 | [`study-schedule-generator`](./study-schedule-generator/SKILL.md) | Create weekly, exam-cram, or assignment-driven study calendars | When student is overwhelmed, exam prep, new term |
| 5 | [`error-pattern-analyzer`](./error-pattern-analyzer/SKILL.md) | Diagnose mistake patterns from wrong answers by type and root cause | After failed tests, "same mistake again" moments |
| 6 | [`concept-explainer`](./concept-explainer/SKILL.md) | Generate tailored mini-lessons with analogies, worked examples, and checks | Student says "I don't get it," conceptual gaps |
| 7 | [`homework-tracker`](./homework-tracker/SKILL.md) | Running log of assignments, due dates, completion status, and barrier diagnosis | End of every session; weekly homework check-in |
| 8 | [`parent-update-drafter`](./parent-update-drafter/SKILL.md) | Draft after-session texts, weekly emails, and formal progress reports | After sessions, weekly rollup, month-end reports |
| 9 | [`exec-function-checkin`](./exec-function-checkin/SKILL.md) | Assess 8 executive functioning domains with scored profiles and interventions | Baseline intake, monthly check-ins, EF concern flags |
| 10 | [`exam-prep-checklist`](./exam-prep-checklist/SKILL.md) | Phased exam preparation checklists with daily tasks and format strategies | 1-3 weeks before any exam or major test |
| 11 | [`spaced-repetition-planner`](./spaced-repetition-planner/SKILL.md) | Review schedules at optimal intervals to combat forgetting | After teaching new concepts, exam prep, retention plans |
| 12 | [`student-profile-card`](./student-profile-card/SKILL.md) | One-page living reference: strengths, preferences, watch areas, what works | Intake, handoffs between tutors, semester updates |

---

## Skill Ecosystem — How They Connect

```
                    student-profile-card
                           |
        +------------------+------------------+
        |                  |                  |
  smart-goals      exec-function      homework-tracker
  -planner           -checkin                |
        |                  |                  |
        +------------------+------------------+
                           |
              session-agenda-builder
                           |
                    [TUTORING SESSION]
                           |
              session-notes-writer
                           |
        +------------------+------------------+
        |                  |                  |
  parent-update      concept-explainer   study-schedule
     -drafter                |             -generator
                            |                  |
                      error-pattern      exam-prep-checklist
                       -analyzer              |
                            |                  |
                     spaced-repetition <-------+
                         -planner
```

### Integration Points

| When this happens... | These skills connect |
|---|---|
| Student has an upcoming exam | `exam-prep-checklist` → `error-pattern-analyzer` for practice test review → `spaced-repetition-planner` for topic review |
| New student intake | `student-profile-card` (CREATE) → `exec-function-checkin` (baseline) → `smart-goals-planner` (initial goals) |
| Start of session | `session-agenda-builder` pulls from `homework-tracker` (status check) + `student-profile-card` (what works) |
| End of session | `session-notes-writer` records outcomes → `homework-tracker` logs new assignments → `spaced-repetition-planner` schedules review of new concepts |
| Weekly cycle | `session-notes-writer` (rollup) → `parent-update-drafter` (weekly email) + `study-schedule-generator` (next week's plan) |
| Monthly cycle | `exec-function-checkin` (re-check) + `smart-goals-planner` (goal review) + `parent-update-drafter` (formal report) |
| Student says "I don't get it" | `concept-explainer` teaches → `error-pattern-analyzer` diagnoses practice problems → `spaced-repetition-planner` locks it in |

---

## Installation

Each skill is packaged as a `.skill` file. To install:

1. Download the `.skill` files from the `/skills/` directory
2. Place them in your Claude skills directory:
   - Built-in: `/app/.agents/skills/{skill-name}/SKILL.md`
   - User skills: `/app/.user/skills/{skill-name}/SKILL.md`
3. Each `.skill` file unpacks to a folder containing its `SKILL.md`

---

## Design Principles (Applied Across All Skills)

1. **Simple workflows** — 3-6 steps max, completable in under 5 minutes
2. **Repeated tasks** — Every skill solves something a tutor does 10+ times per month
3. **Self-contained** — Claude can execute without guessing; no external dependencies
4. **Dual-audience aware** — Most skills produce both tutor-facing and student/parent-facing output
5. **Living documents** — Trackers and profiles are updated, not recreated
6. **Specific over vague** — "8/10 correct" not "did well"; "p. 45-47 odd" not "study Chapter 5"
7. **Integrated ecosystem** — Skills reference each other at natural connection points

---

## Quality Metrics

| Metric | Value |
|--------|-------|
| Total skills | 12 |
| Total lines of instruction | ~3,600 |
| Average skill length | ~300 lines |
| Workflow steps per skill | 4-6 |
| Average completion time | < 5 minutes |
| Integration points between skills | 15+ |

---

*Generated for general subjects and executive functioning tutoring workflows.*
