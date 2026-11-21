# Report: rebuilding assessment-designer

## The problem

The pipeline was missing the agent that writes each module's quiz, instructor key, and TA feedback
pack. Before any change, the agent tests failed (`test_exactly_the_expected_agents`) and the
checker reported three blocking `MANIFEST-MISSING` findings for the quiz files.

## What I built

I read the spec, the three templates, and the quiz part of `scripts/check_package.py`
(`check_quizzes`, `check_key`, `check_ta_packs`, `check_wall`). Then I wrote the agent with the
same structure as `lab-engineer.md`: front matter, what it may write, the student and instructor
wall, inputs, rules for each of the three files, a self-check list, and the report block.

I put the wall near the top and said why it matters: the ta-agent reads the TA pack and talks to
students, so anything in the pack can reach a student. The checker also blocks the phrase
"is correct" anywhere in the TA pack, so the agent is told to avoid it in every sentence.

**Model:** `sonnet`. It matches `deck-writer` and `lab-engineer`, which run at the same stage. It
also costs less per run, which matters because the agent is rerun after every fix. The checker and
my own hand check catch quality problems that a cheaper model might miss.

## What went wrong, and what I changed

**Round 1** passed the checker with 0 blocking findings. A QA review then found that Q5 invented
error wording: a classmate said "the error says the list has no Blue Windows". Nobody had run the
code, so that text came from nowhere. When I ran the same `remove()` call myself, Python printed
`ValueError: list.remove(x): x not in list`, which is different. Invented output teaches students
to trust text that will not match their screen.

**Round 2.** I did not edit the quiz by hand. I added two rules to the agent:

- Rule 10: never quote, paraphrase, or have a character describe printed text unless it is
  recorded in the source pack or in captured output. Name only the error type and the line.
- Rule 11: if the syllabus asks for captured output and none exists, work it out by hand, label
  it, and list the item under `NEEDS A HUMAN`.

The rerun quiz names only `ValueError` and line 3, labels Q5's output as hand-worked, and flags Q5
for a human. Checker: 0 blocking, 2 minor.

## Three hand-checked questions

I checked each answer by running the code in Python.

- **Q3, `append()` returns `None`.** Key says D (5, then `None`). Python printed `5` and `None`.
  Right. The code is short and clear for a high school student, and every wrong option has a
  misconception line. Option C comes from a sourced misconception (SP-1.4).
- **Q4, `songs.remove(1)`.** Key says A (stops with a `ValueError`). Python raised `ValueError`.
  Right, and the stem names the error type without inventing its wording. Weakness: two wrong-option
  explanations (B, D) rest on misconceptions the source pack only marks as hypotheses.
- **Q7, counter starts at 0.** Key says B (numbers run 0 to 3). Python printed 0 to 3. Right, and it
  is a fair judgement item: the songs are right but the numbers are wrong. Weakness: the output is
  labelled hand-worked although it takes seconds to run, and the explanation for option D is a guess.

## Limits

- Q5 still uses hand-worked output. The syllabus asks for output captured by running the lab's
  starter, and nobody has run it (QA-16). I left this as a known limit, because fixing it means a
  real run or a syllabus change, which is outside this task.
- Q8 is a near transfer: the same list steps on homework tasks instead of songs.
- The Q5 and Q8 key headings are long sentences, which caused a minor `HEADING-CASE` finding.
