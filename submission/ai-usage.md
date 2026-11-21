# AI usage

## How I used AI

- **Claude (chat)** helped me read the spec, the templates, and `scripts/check_package.py`, and
  turn them into a list of rules the quiz, key, and TA pack must follow. It drafted
  `assessment-designer.md` from that list, using `lab-engineer.md` as the structure.
- **Claude Code** ran the agent on the sample course, twice.
- After round 1, Claude helped me turn the QA-17 finding into a rule for the agent (rules 10 and
  11), instead of editing the quiz by hand.

## What I decided and checked myself

- I chose `sonnet` as the model, for cost and to match the other agents at the same stage.
- I ran the tests and the checker myself, in the terminal, before and after.
- I checked three answers by running the code in Python. That run also showed that the round 1
  error wording was invented.
- I only committed my own files. After the first run, Claude Code had also changed `STATUS.md` and
  two QA files while preparing Gate 2. I restored those, because they are not part of this task.

## A suggestion I did not take

After round 1, Claude Code kept going past my agent. It ran a QA review and tried to open Gate 2.
It recommended that I either run the lab's starter and paste the output, so it could rerun the deck
and quiz writers, render, and redo QA, or change the syllabus rule and take Gate 1 again.

I did neither. This task is to rebuild one agent and pass the checker through production. Gate 2
and the syllabus are outside it, and changing an approved syllabus to make my own quiz pass would
be the wrong fix. Instead, I fixed the real fault in my agent (it invented error wording), recorded
the captured-output gap as a known limit in `report.md`, and told Claude Code to run only my agent
next time and stop after its report.
