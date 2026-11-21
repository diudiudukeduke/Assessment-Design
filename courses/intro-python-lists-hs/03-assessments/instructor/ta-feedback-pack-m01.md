---
course: intro-python-lists-hs
stage: 03-assessments/instructor
module: 01
author: assessment-designer
date: 2026-11-20
outcomes: LO-1, LO-2, LO-3, LO-4, LO-5
---

# TA feedback pack: module 01

Safe for the ta-agent. Contains criteria and misconception explanations only. No literal answers,
no solutions, no answer letters. Write it assuming a student will read it.

## What each quiz item measures

| Item | Outcome | What it checks | Common confusion, explained without the answer |
| --- | --- | --- | --- |
| Q1 | LO-2 | Choosing the expression that reads the first item of a list | In daily life people count from one, so they carry that habit into the brackets. Some also mix up a number that counts items with a number that names a position, or think a list is looked up by a title. |
| Q2 | LO-2 | Relating the item count, the last valid index, and what an index past the end does | Learners treat the count and the last index as the same number. Some expect a missing position to give back nothing and let the program carry on. Ask what "distance from the start" means for the first item. |
| Q3 | LO-3 | What `append()` changes, and what a method hands back | Many functions give back a result, so learners expect the same here. The change to the list is a side effect, which is separate from the value the call hands back. |
| Q4 | LO-3 | Whether `remove()` works by value or by position | The brackets and number look like indexing, and the word "remove" sounds like "delete this spot". Some learners also think a delete that matches nothing is quietly ignored. |
| Q5 | LO-5 | Reading an error for its type and its line, then deciding which side of a mismatch to change using the written specification | Learners fix whichever side is easiest, not the side the specification protects. Many also read a run that printed nothing as proof that the whole file is wrong, or as proof that it is fine. |
| Q6 | LO-4 | What the loop variable holds on a pass | Learners expect a loop to hand out positions, as loops do in some other languages. The loop variable is a name for what the list holds, not for where it sits. |
| Q7 | LO-4 | Judging a printout against a written numbering rule | A printout that looks tidy, has no error, and shows every song feels finished. The rule about where numbering starts and ends gets forgotten. Ask the learner to read the rule first, then the first and last lines. |
| Q8 | LO-1 | Applying the whole build sequence to a new list, with the data in a different state | Learners copy the song program and keep its results without re-deriving what the list holds at the moment each print runs. Ask them to write the list's contents after each change before they write the print lines. |

## Lab rubric criteria

Each criterion is something a grader can see in the learner's `playlist.py`, their lab notes, or their run.

- The run prints the lab's expected-output block, line for line, with nothing before or after it. The `setup ok` line is gone.
- The file has a line that calls `append()` with "Garden Song" on its own line, above the line that prints the count.
- The `remove()` line names a title that matches a list item letter for letter, and the list line still matches the starter.
- The learner's Step 3 notes name the error type and the line number the error pointed to, and say what they compared.
- The learner's Step 3 notes include a prediction written before the run, and a sentence after the run saying whether it held. The prediction is not marked for being right.
- The counter variable is set on a line above the `for` line, and the add-one line is indented inside the loop.
- The learner can point to the line that changed the list in Step 2 and the line that changed it in Step 3, and says in one sentence why each one changes it.
- The file uses no `if`, `enumerate()`, `range()`, `try`, or `except`.
- If the learner did the extension with their own titles, the notes say it was not compared against the expected-output block.

## Hints that do not give the answer

- "Point at the first title in the list. How many titles come before it? What does that tell you about its index?"
- "What number does `len()` give for this list? What is the position of the last title? Are those the same number?"
- "When you call `append()` on its own line, what changes? When you store the call in a variable, what does the variable hold? How could you check?"
- "What does `remove()` compare against: the position of an item or the item itself? How would you test that with a list of your own?"
- "Read the last line of the error. What is the error type? Which line number does it name? Open that line."
- "Put the name in the `remove()` line next to the matching list title. Read both letter by letter. What do you notice?"
- "Which part of the written specification can you not change? Which part of the code is allowed to change?"
- "What does the program print when an error stops it on line 3? Do lines 4 and 5 get a turn?"
- "On the first pass of the loop, what would you see if you printed the loop variable by itself?"
- "Trace the counter by hand. What is its value when the first line prints? What is it on the last line? Now read the numbering rule."
- "Before you write the print lines, write out what the list holds after each change. Which item sits at the front at that point?"
- "Does the order of your lines matter? What does a print line see if it sits above or below the line that changes the list?"
