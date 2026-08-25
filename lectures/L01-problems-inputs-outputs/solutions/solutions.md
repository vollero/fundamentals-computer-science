# L01 in-class exercises — Worked solutions

These are model answers. Equivalent precise wording is acceptable where noted.

## Retrieval warm-up

1. A broad goal describes a desired improvement but can leave its evidence and
   behavior open to interpretation. A computational problem identifies
   representable inputs, required outputs, and sufficiently precise constraints
   or success conditions for us to test a result.
2. Example: a building name is an input; a route to its accessible entrance is
   an output. Many alternatives are valid if the direction is stated correctly.
3. A program is a representation of instructions. An executor is the system that reads
   and carries out those instructions during a run.

Common misconception: “The program is the computer.” A stored program is data
until a suitable system executes it.

## Repair the request

1. “Make the library better” leaves the intended output and success criterion
   undefined. It also supplies no inputs or rules. “Better” requires a human
   decision before implementation.
2. “Something” does not define accepted input; “useful information” does not
   define required output or success. Rules and boundary cases are also absent.
3. This is closer: it suggests a title input and an availability output. It is
   still ambiguous about matching rules, duplicate titles, empty input, and the
   exact output alternatives.

One valid rewrite is:

> Accept a complete book title as text. If the input is non-empty, find exact
> title matches in the current catalog. Display `AVAILABLE` if at least one
> matching copy is marked available, `UNAVAILABLE` if matches exist but no copy
> is available, and `NOT FOUND` if no title matches. If the input is empty,
> display `TITLE REQUIRED`.

This answer chooses policies; other policies are acceptable if they resolve the
same ambiguities. For example, a design could return every matching edition.

Common misconception: specifying screen colors or button placement instead of
observable problem behavior. Interface design may matter later, but it does not
replace input/output rules.

## Specify a black box

One valid model is:

```text
current people count --> compare count with safe capacity 8 --> ENTER / FULL
```

Assumptions:

- the normal input is one whole-number count from 0 upward;
- the sensor report describes the current room state;
- capacity 8 is fixed for this specification;
- sensor readings are trusted in normal cases.

Rules and exact outputs:

- For counts 0 through 7, output `ENTER`.
- For count 8 or greater, output `FULL`.

Example pairs:

| Input | Output | Reason |
| ---: | --- | --- |
| 7 | `ENTER` | One place remains. |
| 8 | `FULL` | Capacity is the boundary and has been reached. |
| 9 | `FULL` | The reported count is above capacity. |

Unresolved cases could include a negative report, a missing reading, a fractional
reading, a sensor that has not updated after somebody enters, or disagreement
about whether a person at the doorway is already counted. The important point is
to expose rather than silently resolve the ambiguity.

Common misconception: outputting `ENTER` for 8 because eight people are allowed.
The question is whether another student should enter; at 8, the room is already full.

## Predict, run, and modify Python

Expected original sequence:

1. `Welcome to Fundamentals of Computer Science.` appears, followed by a new line.
2. `Press Enter when you are ready.` appears on its own line.
3. `input()` waits without producing more output.
4. The learner presses Enter, causing an empty line to be submitted as runtime input.
5. `The first activity has started.` appears.
6. Execution reaches the end of the file and the run finishes.

A correct `classroom_welcome.py` is:

```python
print("Welcome to room 101.")
print("Press Enter when you are ready.")
input()
print("Let us begin.")
```

For the first run with an empty submitted line, the program-produced text is:

```text
Welcome to room 101.
Press Enter when you are ready.
Let us begin.
```

On the second run, the program receives the text `not ready`, but its later
program-produced output does not change. The prompt communicates a request; it
does not validate readiness. This program discards the received value.

Common errors:

- writing `Print` instead of lowercase `print`;
- omitting or mismatching quotation marks or parentheses;
- changing the requested punctuation or capitalization;
- confusing the submitted runtime line with source code;
- claiming the entered information changes later output when the program discards it.

## Exit ticket

1. Labels:
   - `print("Done")` in the file: **source code**;
   - displayed `Press Enter.` prompt: **runtime output**;
   - empty line submitted when the learner presses Enter: **runtime input**;
   - displayed `Done`: **runtime output**.
2. `Done` is produced only after the earlier instructions complete, so observing
   it is evidence that this run reached the fourth line. The source contains no
   statement of a real-world goal or success criterion, so that observation alone
   cannot establish usefulness or correctness against an unstated problem.
3. A suitable bridge question is: “What kinds of values can Python represent,
   and what operations can a program perform on them?” Equivalent questions
   about using received input are acceptable.

## Optional extension

The official documentation says that `input()` reads a line, removes the trailing
newline, and returns the result as a string. L01 does not yet retain that returned
value. A useful next question is: “How can we give the returned value a name so a
later instruction can use it?” Values are introduced in L02 and assignment in L03.

## Exit-ticket rubric (5 points)

| Evidence | Points |
| --- | ---: |
| All four source/input/output labels correct | 2 |
| Explanation distinguishes execution evidence from problem correctness | 2 |
| Bridge question concerns values, operations, or retaining/using input | 1 |

- **5:** ready for L02.
- **3–4:** review the three-channel distinction before L02.
- **0–2:** repeat the trace with an instructor or peer and resubmit.

## Whole-session formative rubric (10 points)

| Evidence | 2 — Secure | 1 — Developing | 0 — Missing |
| --- | --- | --- | --- |
| Problem specification | Accepted input, exact outputs, rules, and success evidence are stated | One element remains ambiguous | Goal remains non-testable |
| Black-box reasoning | Rules, boundary at 8, and unresolved cases are correct | Mostly correct with one gap | Rule or boundary is fundamentally incorrect |
| Three-channel distinction | Source, prompt output, user input, and execution output are separated | One classification error | Categories are substantially confused |
| Python execution | Ordered prediction; modified program runs with exact messages and pause | Minor syntax, text, or order issue | Does not run or meet required behavior |
| Testing and explanation | Normal and off-prompt runs support a correct explanation | Tests performed but explanation incomplete | No testing evidence |

- **9–10:** ready for L02.
- **7–8:** review the one developing category.
- **5–6:** revise with peer or instructor guidance.
- **0–4:** repeat the execution trace with support before continuing.
