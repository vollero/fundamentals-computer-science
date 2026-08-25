# L01 in-class exercises — From a request to a first run

**Class time:** 45 minutes  
**Mode:** individual work, pairs, a small group, then individual exit ticket  
**Required:** Python 3.12 or later and the L01 `code/` directory

Do not open the solutions until the instructor ends the activity.

## 0–5 min — Retrieval warm-up (`core`)

Answer individually in one or two sentences each.

1. What is the difference between a broad goal and a computational problem?
2. Give one possible input and one possible output for a campus navigation system.
3. What is the difference between a program and an executor?

## 5–15 min — Repair the request (`core`)

Work with a partner. For each request, identify what prevents it from being a
testable computational problem. Label each missing element as one or more of:
`input`, `output`, `rule`, `boundary case`, or `success criterion`.

1. “Make the library better.”
2. “Given something about a book, show useful information.”
3. “Given a title, show whether the library has the book.”

Rewrite request 3 so that it states:

- what input is accepted;
- exactly which output alternatives are possible;
- what happens when several books have the same title;
- what happens when the input is empty.

Your rewrite need not describe a user interface or an implementation.

## 15–27 min — Specify a black box (`practice`)

Work in a group of three. The **specifier** drafts inputs, rules, and outputs; the
**skeptic** finds ambiguity and boundary cases; the **tester** proposes examples.

A classroom display should help students decide whether to enter a study room.
The available sensor reports the number of people currently in the room. The
room's safe capacity is 8.

1. Draw an input–rules–output diagram and state your input assumptions.
2. Write the normal-case rule and exact output alternatives.
3. Give three example input/output pairs: below, at, and above capacity.
4. Identify one boundary or failure case the description has not resolved.

Do not write Python. Selection is introduced formally in L05; here the goal is a
clear specification.

## 27–38 min — Predict, run, and modify Python (`practice`)

Work individually for this section.

1. Open `code/welcome_pause.py` without running it.
2. Write the exact observable event sequence you predict. Include when the
   program waits and when it finishes.
3. Run the program. Record one difference between your prediction and observation,
   or write “no difference.”
4. Open `code/classroom_welcome_starter.py`, save your own copy as
   `classroom_welcome.py`, and change it so a run:
   - displays `Welcome to room 101.` on its own line;
   - displays `Press Enter when you are ready.` on its own line;
   - waits for a submitted line;
   - after Enter, displays `Let us begin.` on its own line.
5. Predict the modified behavior and verify the exact text and order.
6. Run it twice:
   - first, press Enter without typing text;
   - second, type `not ready` and then press Enter.
7. Record what the program received, whether its later output changed, and
   whether the program actually ensured that you were ready. Explain the result
   in one sentence.

Use only `print()` and `input()`. Do not add variables, conditions, loops, or
features copied from the internet.

## 38–40 min — Peer verification

Exchange seats with a partner without changing their file. Check the exact
messages, order, waiting behavior, and two-run explanation. Return the file and
resolve one difference using observed evidence.

## 40–45 min — Individual exit ticket (`core`)

Submit answers individually.

Consider this source file:

```python
print("System check")
print("Press Enter.")
input()
print("Done")
```

1. Label each of the following as **source code**, **runtime input**, or
   **runtime output**:
   - the characters `print("Done")` in the file;
   - the prompt `Press Enter.` displayed on screen;
   - the empty line submitted when the learner presses Enter;
   - the word `Done` displayed on screen.
2. Explain why observing `Done` proves that execution reached the fourth line but
   does not prove that the program solves a useful real-world problem.
3. Write the question that L02 now needs to answer.

## Optional extension (`extension`, 10–20 min outside contact time)

Read the official Python documentation for [`input()`](https://docs.python.org/3.14/library/functions.html#input).
Find what value `input()` makes available after Enter is pressed. Do not use that
value in code yet. Write one question about how a later program might retain it.

## Progressive hints

Use the first relevant hint only after making a genuine attempt.

1. **Request repair:** underline information crossing into or out of the proposed
   system. Circle words such as “better” and “useful”; each needs a policy or
   success criterion.
2. **Black box:** test one count below capacity, exactly at capacity, and above
   capacity. Is the advice about the room before or after one more person enters?
3. **Execution trace:** follow one source line at a time. The second `print()`
   produces the prompt; `input()` then waits.
4. **Python syntax:** preserve lowercase spelling, quotation marks, and matching
   parentheses. If the run seems frozen, check whether it is waiting for input.
5. **Exit ticket:** classify by origin and direction—written before execution,
   entering during execution, or leaving during execution.
