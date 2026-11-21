---
course: intro-python-lists-hs
stage: 03-assessments/student
module: 01
author: assessment-designer
date: 2026-11-20
outcomes: LO-1, LO-2, LO-3, LO-4, LO-5
---

# Quiz: Build playlist.py, keep a class playlist in a Python list

Answer every question. Multiple choice questions have one correct answer unless stated. Questions 5, 7, and 8 need a written answer. Where a question shows output, it was worked out by hand from the code. Nobody ran it.

## Question 1

<!-- item: Q1 | outcome: LO-2 | difficulty: basic -->

The class playlist is stored like this.

```python
songs = ["Sunrise Walk", "Blue Window", "Paper Planes", "Night Bus"]
```

Which expression gives the first song, "Sunrise Walk"?

A. `songs[1]`
B. `len(songs)`
C. `songs[0]`
D. `songs["Sunrise Walk"]`

## Question 2

<!-- item: Q2 | outcome: LO-2 | difficulty: basic -->

The class playlist `songs` holds four songs: "Sunrise Walk", "Blue Window", "Paper Planes", and "Night Bus". An `IndexError` is the error Python gives when an index does not exist. Which statement is true?

A. `len(songs)` is 4, the last valid index is 3, and `songs[4]` stops the program with an `IndexError`.
B. `len(songs)` is 4, the last valid index is 4, and `songs[4]` gives "Night Bus".
C. `len(songs)` is 3, the last valid index is 3, and `songs[4]` stops the program with an `IndexError`.
D. `len(songs)` is 4, the last valid index is 3, and `songs[4]` gives an empty value while the program keeps running.

## Question 3

<!-- item: Q3 | outcome: LO-3 | difficulty: basic -->

The class playlist `songs` holds four songs. This line runs once.

```python
result = songs.append("Garden Song")
```

Which statement is true after the line runs?

A. `len(songs)` is 4, and `result` holds a new list with five songs.
B. `len(songs)` is 5, and `result` is `None`.
C. `len(songs)` is 5, and `result` holds the list with five songs.
D. `len(songs)` is 5, and `result` is "Garden Song".

## Question 4

<!-- item: Q4 | outcome: LO-3 | difficulty: standard -->

The class playlist holds these songs, in this order: "Sunrise Walk", "Blue Window", "Paper Planes", "Night Bus". This line runs.

```python
songs.remove(1)
```

What happens?

A. It removes "Blue Window", the item at position 1.
B. It removes "Sunrise Walk", the first item when you count from 1.
C. It does nothing, and the program keeps running with all four songs.
D. It stops the program with a `ValueError`, because no item equals 1.

## Question 5

<!-- item: Q5 | outcome: LO-5 | difficulty: standard -->

**Requirement:** The class's four starting titles are fixed, and they include "Blue Window". The finished program must remove "Blue Window" and end with four songs and no error.

Here is a version of the file, with line numbers.

```text
1  songs = ["Sunrise Walk", "Blue Window", "Paper Planes", "Night Bus"]
2  songs.append("Garden Song")
3  songs.remove("Blue Windows")
4  print("Songs:", len(songs))
5  print("First song:", songs[0])
```

The result, worked out by hand from these five lines. Nobody ran this file, so it is not a captured run.

```text
Lines 1 and 2 run. The list now holds five songs.
Line 3 asks to remove "Blue Windows". No item equals that text.
Python stops at line 3 with a ValueError.
Lines 4 and 5 never run, so the program prints nothing.
```

A classmate says: "The error says the list has no Blue Windows, so I will add an s to the title on line 1."

Which line should change, and why? What does this result prove, and what does it not prove?

## Question 6

<!-- item: Q6 | outcome: LO-4 | difficulty: basic -->

After the append and remove steps, the class playlist holds, in order: "Sunrise Walk", "Paper Planes", "Night Bus", "Garden Song". This loop runs.

```python
for song in songs:
    print(song)
```

On the first pass of the loop, what does the loop variable `song` hold?

A. 0
B. "Sunrise Walk"
C. 1
D. 4

## Question 7

<!-- item: Q7 | outcome: LO-4 | difficulty: standard -->

**Requirement:** The numbers in the printout must run from 1 up to the number of songs, one number per song, in list order.

The class playlist `songs` holds, in order: "Sunrise Walk", "Paper Planes", "Night Bus", "Garden Song". A student writes this loop.

```python
number = 0
for song in songs:
    print(number, song)
    number = number + 1
```

The output, worked out by hand from the code. Nobody ran it, so it is not a captured run.

```text
0 Sunrise Walk
1 Paper Planes
2 Night Bus
3 Garden Song
```

The student says: "All four songs print, in order, with no error, so this meets the requirement."

Is the student right? What does this output prove, and what does it not prove?

## Question 8

<!-- item: Q8 | outcome: LO-1 | difficulty: stretch -->

**Transfer.** A student keeps homework in a list. This is the request, in the student's words: "Start with three tasks: Math sheet, Read chapter, Lab report. Add Essay outline. Drop Math sheet, because it is finished. Then show how many tasks are left, which task is first, and every task numbered from 1."

Write the Python program for this request. Use a list named `tasks`. Use only what you learned in this module. Then write the lines your program prints. The wording of the labels is yours.

## Predict and reflect

Neither of these is graded for being right.

**Predict.** Before you run Step 3 of the lab, write what you expect to see when you turn on the starter's `remove()` line. Write whether the two `print()` lines below it will print anything.

**Reflect.** After the step, write what actually happened and whether your prediction held. Say what you would check first the next time a run stops with an error.
