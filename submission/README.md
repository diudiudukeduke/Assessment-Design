# Submission: 5a guided brief, rebuild the quiz agent

**Task:** Guided (5a). I rebuilt the missing `assessment-designer` agent from
`specs/assessment-designer-spec.md`, ran it on `intro-python-lists-hs` module 1, and fixed it until
the checker showed no blocking findings.

**Built:** `.claude/agents/assessment-designer.md`. It writes the student quiz, the instructor key,
and the TA feedback pack, and keeps a hard wall between student and instructor files.

## Commits

| Point | Commit | What it holds |
| --- | --- | --- |
| Before | `14de437` | `qa-report-before.md`, taken before any change |
| Round 1 output | `442364e` | First quiz, key, and TA pack written by the agent |
| After | `83a6f92` | Round 2 output from the fixed agent, and `qa-report-after.md` |

## Result

| Check | Before | After |
| --- | --- | --- |
| Agent tests | 1 failure | 11 of 11 pass |
| Checker, through production, no PDF | 3 blocking, 1 minor | 0 blocking, 2 minor |

The two minor findings are both `HEADING-CASE`. One is the known false positive on the deck. The
other is a long Q5 heading in the key. Neither blocks.

## Files

- `quiz-after.pdf`: the quiz the agent wrote, as rendered, unedited
- `qa-report-before.md`, `qa-report-after.md`: test and checker output
- `report.md`: what went wrong, what I changed, and three hand-checked questions
- `ai-usage.md`: how I used AI, and one suggestion I did not take
