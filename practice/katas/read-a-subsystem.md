# Kata — read a subsystem you did not write

The original form, and the only one here proven by repetition before it was written down.
Highest-yield staff habit in the whole practice: most of what separates senior from staff
is having read more of the system than you were assigned.

## Form

1. Pick one subsystem. Not a file — a boundary with a name.
2. Read it without running it. No debugger, no logs, no tests. Twenty minutes, timed.
3. Draw the data flow from memory before looking again.
4. Write down **one thing that surprised you**, and why you expected otherwise.
5. Only then, check yourself against the code.

## Subject selection

Rotate the origin, not just the target. Something you own → something you depend on →
something that pages someone else. If you pick only what you own, this becomes revision.

## Record

- The surprise, in one sentence.
- The expectation it violated. This is the part that compounds — a wrong model named is
  worth more than a right one confirmed.
- Time to first orientation: how long before you could say what the thing is for.

## Signal to watch

Orientation time falling across reps on *unfamiliar* code. Falling time on familiar code
means nothing. If the surprise column is ever empty, you read too shallow, not too well.
