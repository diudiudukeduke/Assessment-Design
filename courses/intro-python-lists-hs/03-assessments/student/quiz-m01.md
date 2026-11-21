---
course: intro-python-lists-hs
stage: 03-assessments/student
module: 01
author: assessment-designer
date: 2026-11-20
outcomes: LO-1, LO-2, LO-3, LO-4, LO-5
---

# Quiz: Build playlist.py, a numbered playlist

Answer every question. Multiple choice questions have one correct answer unless stated.

Questions 1 to 4, 6, and 7 use the class playlist from the lab. The starting list is:

```python
songs = ["Sunrise Walk", "Blue Window", "Paper Planes", "Night Bus"]
```

## Question 1

<!-- item: Q1 | outcome: LO-2 | difficulty: basic -->

In `playlist.py`, the list `songs` holds the four titles above. Nothing has been added or removed yet. Which line gives you the first song, Sunrise Walk?

A. `songs[len(songs) - 1]`
B. `songs[1]`
C. `songs[0]`
D. `songs["Sunrise Walk"]`

## Question 2

<!-- item: Q2 | outcome: LO-2 | difficulty: basic -->

The list `songs` in `playlist.py` holds the four titles above. Nothing has been added or removed. Which statement is true?

A. `len(songs)` gives 3, because the last index is 3.
B. `len(songs)` gives 4, the last index is 3, and a line that uses `songs[4]` stops the program with an `IndexError`.
C. `len(songs)` gives 4, the last index is 4, and `songs[4]` gives Night Bus.
D. `len(songs)` gives 4, the last index is 3, and `songs[4]` gives `None` while the program carries on.

## Question 3

<!-- item: Q3 | outcome: LO-3 | difficulty: basic -->

A student runs these lines in `playlist.py`, starting from the four-song list.

```python
result = songs.append("Garden Song")
print(len(songs))
print(result)
```

What do the two `print()` lines show?

A. 4, then `None`
B. 5, then Garden Song
C. 5, then the list with all five songs
D. 5, then `None`

## Question 4

<!-- item: Q4 | outcome: LO-3 | difficulty: standard -->

Garden Song has been added, so `songs` holds five titles. The class wants Blue Window gone. A student writes this line, thinking the 1 means "the song at position 1".

```python
songs.remove(1)
```

What happens when Python reaches this line?

A. The program stops with a `ValueError` at that line, because no item in the list equals 1.
B. Blue Window is removed, because 1 is its index.
C. Sunrise Walk is removed, because `remove()` counts positions from 1.
D. Nothing changes and the program carries on, because 1 is not a song title.

## Question 5

<!-- item: Q5 | outcome: LO-5 | difficulty: standard -->

**Requirement:** The four starting titles are fixed. After one song is added and one is removed by name, `playlist.py` must run to the end with no error and print the count and the first song.

A student saves this file. The line numbers are in the left column and are not part of the code.

```text
1  songs = ["Sunrise Walk", "Blue Window", "Paper Planes", "Night Bus"]
2  songs.append("Garden Song")
3  songs.remove("Blue Windows")
4  print("Songs:", len(songs))
5  print("First song:", songs[0])
```

No one captured a real run of this file. The result below was worked out by hand from the rules in this course. It gives the error type and the line, and it does not give Python's message text.

```text
Lines printed: none
The run stops at line 3 with a ValueError
```

Answer these three parts.

1. Which line does the `ValueError` point at, and why does nothing print from lines 4 and 5?
2. What does this result prove, and what does it not prove?
3. The requirement fixes the four titles. Which part of the file do you change?

## Question 6

<!-- item: Q6 | outcome: LO-4 | difficulty: basic -->

The playlist now holds Sunrise Walk, Paper Planes, Night Bus, and Garden Song, in that order. This loop runs.

```python
for song in songs:
    print(song)
```

On the second pass through the loop, what does the variable `song` hold?

A. The number 1, the index of the second item
B. The number 2, the count of passes so far
C. Paper Planes
D. Sunrise Walk and Paper Planes, everything seen so far

## Question 7

<!-- item: Q7 | outcome: LO-4 | difficulty: standard -->

**Requirement:** Print every song on its own line with a number in front. For a playlist of four songs, the numbers run 1, 2, 3, 4.

The playlist holds Sunrise Walk, Paper Planes, Night Bus, and Garden Song when this code runs.

```python
number = 0
for song in songs:
    print(number, song)
    number = number + 1
```

The output below was worked out by hand from the code. It was not captured from a run.

```text
0 Sunrise Walk
1 Paper Planes
2 Night Bus
3 Garden Song
```

Which statement is true?

A. It meets the requirement, because every song appears once, in list order.
B. It fails the requirement, because the numbers run 0 to 3 instead of 1 to 4, even though the songs and their order are right.
C. It fails the requirement, because a `for` loop always counts from 0 and cannot be made to start at 1.
D. It fails the requirement, because the numbers should run to 5 after Garden Song was added.

## Question 8

<!-- item: Q8 | outcome: LO-1 | difficulty: stretch -->

**Transfer.** A student keeps homework in a list instead of songs. The list is:

```python
tasks = ["Math sheet", "Read chapter", "Science report"]
```

Write a short program that does these steps, in this order, using only what you learned in this module.

1. Add "Art sketch" to the end of the list.
2. Remove "Math sheet" by name.
3. Print the count, in the form `Tasks:` followed by the number.
4. Print the first task, in the form `First task:` followed by the task.
5. Print every task on its own line, numbered from 1, in the form `1 Read chapter`.

Then write the exact lines your program prints. You can work them out by hand.

## Predict and reflect

**Predict.** Before you run Step 3 of the lab, write what you expect to see when you turn on the starter's `remove()` line. Say whether the two print lines below it will show anything.

**Reflect.** After the step, write what actually happened and whether your prediction held.
Neither answer is graded for being right.
