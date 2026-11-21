---
course: intro-python-lists-hs
stage: 03-assessments/instructor
module: 01
author: assessment-designer
date: 2026-11-20
outcomes: LO-1, LO-2, LO-3, LO-4, LO-5
---

# Instructor key: quiz-m01

Instructor only. Never copy into the student tree.

## Q1 - Answer: C

- A: a student choosing this thinks the first song sits at the "count minus one" index. They have swapped the first index for the last one (SP-1.3).
- B: a student choosing this thinks the first item has index 1, because everyday counting starts at one (SP-1.1).
- **C is correct.** An index is the distance from the start, so the first item has index 0 and `songs[0]` gives Sunrise Walk (SP-1.1).
- D: a student choosing this thinks square brackets accept a title, like `remove()` does. An index must be a position number.

## Q2 - Answer: B

- A: a student choosing this thinks `len()` returns the last index, so they confuse the count with a position (SP-1.3).
- **B is correct.** `len(songs)` counts four items, indexes run 0 to 3, and index 4 does not exist, so Python stops with an `IndexError` (SP-1.2, SP-1.3).
- C: a student choosing this thinks indexes start at 1, so the last index is 4 and `songs[4]` is the fourth song (SP-1.1, SP-1.2).
- D: a student choosing this thinks a missing index quietly gives `None`, as `append()` returns `None`. A missing index stops the program (SP-1.2).

## Q3 - Answer: D

- A: a student choosing this thinks assigning the result of `append()` captures the change, so `songs` stays at four items. `append()` changes `songs` itself (SP-1.4).
- B: a student choosing this thinks `append()` returns the item it added (SP-1.4).
- C: a student choosing this thinks `append()` hands back the changed list, so `result` holds it. This is the sourced misconception where a poster got `None` after `Newlist = List.append(7)` (SP-1.4).
- **D is correct.** `append()` changes the list in place, so `len(songs)` is 5. It returns `None`, so `result` is `None` (SP-1.4).

## Q4 - Answer: A

- **A is correct.** `remove()` compares the value you give with each item and removes the first match. No item equals 1, so Python raises a `ValueError` at that line (SP-1.5, SP-0.6).
- B: a student choosing this thinks `remove(1)` means "remove the item at position 1", because `songs[1]` has the same shape. `remove()` matches by value (SP-1.5, hypothesis in the source pack).
- C: a student choosing this thinks `remove()` takes a position and that positions start at 1 (SP-1.5, SP-1.1).
- D: a student choosing this thinks a delete that matches nothing is harmless. Python raises an error and stops (SP-1.5, hypothesis in the source pack).

## Q5 - Answer: ValueError at line 3, nothing printed because the run stops there; the result proves the name on line 3 matches no item, and does not prove the list is wrong; change the name in line 3 to Blue Window

Source of truth: a written specification, the lab's four starting titles and expected-output block (six lines, four songs remain, no error).
Requirement quoted from the item: "The four starting titles are fixed. After one song is added and one is removed by name, `playlist.py` must run to the end with no error and print the count and the first song."
Boundary check: the name on line 3 is "Blue Windows" and the list holds "Blue Window". They differ by one letter, and `remove()` needs an exact match, so no item equals the name and the verdict is a fail. The titles are fixed by the requirement, so the list is right and the name is wrong. Correcting the name changes only line 3.

Model answer by part:

1. The error points at line 3. Python runs lines top to bottom and an error ends the run at the failing line, so lines 4 and 5 never run (SP-1.5).
2. It proves line 3 asked `remove()` for a title no item equals, and that the program stopped there. It does not prove the list is misspelled, and it does not say which side is wrong. The requirement decides that. It also does not prove that line 2 failed: the run reached line 3, so the append ran.
3. Change the name in line 3 to match the list. Do not change the list.

Marking note for the grader: the item is hand-worked, so the error type and line are given in the stem. Credit a learner who names the type and the line from the stem and gives the reason from the stop rule. Do not require any message wording, because none is taught (SP-U1).

## Q6 - Answer: C

- A: a student choosing this thinks the loop variable holds the index. On the second pass, the index of Paper Planes is 1 (SP-1.6).
- B: a student choosing this thinks the loop variable counts passes (SP-1.6).
- **C is correct.** The loop variable holds each item in list order, so on pass two it holds Paper Planes (SP-1.6, SP-0.5).
- D: a student choosing this thinks the loop variable collects every item seen so far. It holds one item per pass.

## Q7 - Answer: B

- A: a student choosing this checks only the songs and their order and ignores the numbers. The requirement also fixes the numbers.
- **B is correct.** The counter starts at 0 and goes up after the print, so the numbers run 0 to 3. The requirement says 1, 2, 3, 4. The songs and their order are right, so the fault is only the counter start (SP-1.1, SP-1.6).
- C: a student choosing this thinks the loop supplies the numbers, so the start cannot be changed. The counter is a variable you design, and starting it at 1 fixes the output.
- D: a student choosing this counts the removed song, or counts every song ever added. The playlist holds four songs when the loop runs, so the numbers end at 4.

Source of truth for Q7: a written specification, the lab's expected-output block (numbers 1 to 4). Requirement quoted from the item: "For a playlist of four songs, the numbers run 1, 2, 3, 4." Boundary check: 0 is not in 1 to 4, so the first line already fails. The output is hand-worked: the loop prints the counter before adding one, so the four lines carry 0, 1, 2, 3.

## Q8 - Answer: append "Art sketch", remove "Math sheet", print the count 3 and the first task Read chapter, then number the three tasks 1 to 3

Source of truth: the user's request, the five steps in the item.
Requirement quoted from the item: "Remove "Math sheet" by name." and "Print every task on its own line, numbered from 1".
Boundary check: after the append there are four tasks, after the remove there are three, so the count is 3. The first task is now Read chapter, because the removed task was the old first one. The counter starts at 1 and goes up after the print.

One correct program:

```python
tasks = ["Math sheet", "Read chapter", "Science report"]
tasks.append("Art sketch")
tasks.remove("Math sheet")
print("Tasks:", len(tasks))
print("First task:", tasks[0])
number = 1
for task in tasks:
    print(number, task)
    number = number + 1
```

Expected printed lines, worked by hand:

```text
Tasks: 3
First task: Read chapter
1 Read chapter
2 Science report
3 Art sketch
```

What a learner who pattern-matched the capstone would answer instead: they print First task: Math sheet because in the capstone the first song never changed, or they print Tasks: 4 by stopping the count at the append and forgetting the remove. Credit any counter design whose output matches. Accept a different loop variable name.

Grading note: the append and remove lines must come before the print lines, or the output differs. A program that calls `remove()` with a name that is not in the list is a fail for step 2.
