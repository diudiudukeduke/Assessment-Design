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
| Q1 | LO-2 | Choosing the expression that reads the first song from a list | Learners mix up a position with a count, or with the way they number things in daily life. Ask what "index" measures in the deck. |
| Q2 | LO-2 | Linking the count from `len()` to the range of valid indexes, and what happens past the end | Learners treat the count and the last index as the same number. Some think a missing index gives back an empty value instead of stopping the program. |
| Q3 | LO-3 | What `append()` does to the list and what it hands back | Learners expect a method to give back something useful, like a function that returns a result. The change to the list and the value handed back are two separate things. |
| Q4 | LO-3 | `remove()` matches by value, not by position | The number inside brackets after a list name picks a position, so learners expect the same meaning inside `remove()`. Some also think a delete that finds nothing is harmless. |
| Q5 | LO-5 | Reading an error for its type and its line, and judging what a failing run does and does not show | Learners say the list is wrong because it is the first thing they see, or they say the lines after the error ran. Python runs lines top to bottom and the specification, not a guess, decides which side to fix. |
| Q6 | LO-4 | What the loop variable holds on a given pass | Learners think a `for` loop gives them positions or a pass count. Ask what the loop variable held in the deck's four-pass picture. |
| Q7 | LO-4 | Judging numbered output against a written requirement | Learners check that the songs look right and skip the numbers, or they think the loop itself decides where numbering starts. The counter is a variable the learner designs. |
| Q8 | LO-1 | Applying the whole playlist recipe to a new list | Learners copy the song program line by line and keep results that only held for the songs. The order of the lines and which item leaves the list change what later lines see. |

## Lab rubric criteria

- The submitted `playlist.py` prints exactly six lines when the grader runs it and compares with the lab's expected-output block, with no extra line before or after.
- The file holds the first-song line with an index and the count line with `len()`, and the grader can point to each.
- The `append()` call sits on its own line above the print lines, and it is not placed inside `print()` or on the right side of `=`.
- The `remove()` line names a title that matches a list item letter for letter, and the list of starting titles is unchanged from the starter.
- The student's Step 3 notes name the error type, name the line number the error pointed at, and say what they compared to find the fault.
- The student's Step 3 prediction is written before the run, and the reflection says whether it held. Accuracy is not scored.
- The numbered loop has a counter that is set before the `for` line, printed inside the loop, and changed by one inside the loop. The student can say which line changes it.
- The loop variable is used in the `print()` line to show the song, not a number.
- The student can state, in their own words, which value `remove()` looks at and which value `append()` hands back.
- The debrief shows the student compared the full run with the expected-output block line by line, and noted any difference.
- The code uses none of the tools the lab lists as not used: `if`, `enumerate()`, `range()`, `try`, and `except`.

## Hints that do not give the answer

- Index questions: "Point at the first song in the picture. How many songs come before it?"
- Count and index: "Which of the two numbers counts items, and which names a place? Which one starts at zero?"
- `append()` questions: "Two things happen on that line. What changes, and what comes back? Which one does `print()` show?"
- `remove()` questions: "What does `remove()` compare each item with? What does it do when no item matches?"
- Error questions: "Which two facts do you read from an error first? Which line does it name, and did the lines below it run?"
- Which side to fix: "Which document says what the titles must be? Does the list or the name in `remove()` disagree with it?"
- Loop variable: "On pass one of the picture, what is written in the box that `song` points at? What changes on pass two?"
- Numbering: "Trace the first pass by hand. What is the counter when `print()` runs, and what is it after the last line of the loop?"
- Requirement checks: "Read the requirement again. Does each line of the output meet every part of it, or only the part you looked at?"
- New list questions: "Write down the list after each step, one line per step. What does the list hold when each print line runs?"
- Never write the finished program for the student. Ask them to trace one pass and say what they see.
