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

- A: a student choosing this counts from 1 in daily life and thinks the first item has index 1. `songs[1]` gives "Blue Window" (SP-1.1).
- B: a student choosing this confuses the count with a position. `len(songs)` is the number 4, not a song (SP-1.3).
- **C is correct.** The first item is zero steps from the start, so its index is 0 (SP-1.1).
- D: a student choosing this thinks a list is looked up by value, the way `remove()` takes a value. An index must be a number, so this raises an error.

## Q2 - Answer: A

- **A is correct.** `len()` counts items, so it gives 4. Indexes start at 0, so the last valid index is `len(songs) - 1`, which is 3. Index 4 does not exist, so Python raises `IndexError` (SP-1.2, SP-1.3).
- B: a student choosing this believes indexes start at 1, so the last index equals the count (SP-1.1, SP-1.2).
- C: a student choosing this mixes up the count and the last index, and thinks `len()` returns 3 for four items (SP-1.3).
- D: a student choosing this thinks a missing index is harmless and returns nothing. Python stops the program instead (SP-1.2).

## Q3 - Answer: B

- A: a student choosing this thinks `append()` leaves the old list alone and hands back a new one.
- **B is correct.** `append()` changes the list in place, so `len(songs)` is 5. It returns `None`, so `result` is `None` (SP-1.4, SP-0.6).
- C: a student choosing this thinks a method returns the changed list, the same belief as the forum poster who got `None` after `Newlist = List.append(7)` (SP-1.4).
- D: a student choosing this thinks a method hands back the item it added. It hands back nothing (SP-1.4).

## Q4 - Answer: D

- A: a student choosing this thinks `remove(1)` means position 1, because `songs[1]` uses a number in the same shape (SP-1.5).
- B: a student choosing this thinks `remove(1)` means "the first item", counting from 1 (SP-1.5, SP-1.1).
- C: a student choosing this thinks a delete that matches nothing is ignored (SP-1.5).
- **D is correct.** `remove()` compares its value with each item using equality. The list holds only text, so no item equals 1. Python raises `ValueError` and the program stops at that line (SP-1.5, SP-0.6).

## Q5 - Answer: change line 3, not line 1. Line 3 names a title that is not in the list, so `remove()` raises a `ValueError`. The result proves where the run stopped. It does not prove the rest of the file is right.

Source of truth: a written specification, the four starting titles in the starter file and the lab's expected-output block (four songs left, no error).
Requirement quoted from the item: "The class's four starting titles are fixed, and they include "Blue Window". The finished program must remove "Blue Window" and end with four songs and no error."
Boundary check: "Blue Windows" and "Blue Window" differ by one letter. `remove()` needs exact equality, so there is no match and the run stops at line 3 (SP-1.5). Changing line 1 would break the fixed titles, so the verdict on the classmate's plan is wrong. The fix is the name on line 3, and line 1 stays as it is.

What a full answer says:

- It proves that line 3 is where the run stops, that the error type is `ValueError`, and that lines 4 and 5 never ran.
- It does not prove that lines 4 and 5 are right, because they never ran. It does not prove the final output, and it does not give the message wording, which the course has not captured (SP-U1).
- The error alone does not say which side is wrong, the name or the list. The written specification decides that, and it fixes the titles.

Full credit needs the line number, the reason (exact match fails), and one limit of the result. A student who only says "fix the typo" gets partial credit.

## Q6 - Answer: B

- A: a student choosing this thinks the loop variable counts indexes starting at 0 (SP-1.6).
- **B is correct.** A `for` loop gives the loop variable each item in list order, so the first pass holds "Sunrise Walk" (SP-1.6, SP-0.5).
- C: a student choosing this thinks the loop variable counts passes starting at 1 (SP-1.6).
- D: a student choosing this thinks the loop variable holds the number of songs. It holds one song per pass.

## Q7 - Answer: no, the student is wrong. The output proves every song printed once, in order, with no error. It does not prove the numbers are right, and they are not: they run 0 to 3 instead of 1 to 4.

Source of truth: a written specification, the lab's expected-output block, whose numbered lines run 1 to 4.
Requirement quoted from the item: "The numbers in the printout must run from 1 up to the number of songs, one number per song, in list order."
Boundary check: 0 is below the allowed start, and the last number is 3 where the count of songs is 4, so the output fails at both ends. Start the counter at 1 and add one after the print. The printout is by hand and no run is claimed (SP-1.6).

What a full answer says:

- It proves the loop visited all four songs, in list order, and nothing stopped it.
- It does not prove the numbering. A printout can look tidy and still be off by one, and only the written requirement catches it.

## Q8 - Answer: a program that builds the list, appends, removes by name, then prints the count, the first task, and every task numbered from 1. It prints a count of 3, first task "Read chapter", and three numbered lines.

Source of truth: the user's request, quoted in the item.
Requirement quoted from the item: "Add Essay outline. Drop Math sheet, because it is finished. Then show how many tasks are left, which task is first, and every task numbered from 1."
Boundary check: the removed task, "Math sheet", is the first item, so the first task after the change is "Read chapter". The count after one add and one removal is 3. Numbers run 1, 2, 3.

Model program:

```python
tasks = ["Math sheet", "Read chapter", "Lab report"]
tasks.append("Essay outline")
tasks.remove("Math sheet")
print("Tasks:", len(tasks))
print("First task:", tasks[0])
number = 1
for task in tasks:
    print(number, task)
    number = number + 1
```

Model output:

```text
Tasks: 3
First task: Read chapter
1 Read chapter
2 Lab report
3 Essay outline
```

Rests on SP-1.1, SP-1.3, SP-1.4, SP-1.5, SP-1.6. Any counter name, any label wording, and any equivalent order that puts the `append()` and `remove()` lines before the prints are fine.

What a learner who pattern-matched the capstone would answer instead: a first task of "Math sheet" (the capstone's first song never leaves the list), or a count of 4 or numbers running to 4, from copying the song program's output.

Marking notes for the human grader: look for exact title matches in `remove()`, no `if`, `range()`, or `enumerate()`, the counter set before the loop, and the add-one line inside the loop.
