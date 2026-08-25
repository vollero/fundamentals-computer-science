# Running the L01 examples

The course reference implementation is CPython 3.14. These L01 examples also
support Python 3.12 and later.

Use the Run button in the course editor, or open a terminal in this directory and
run:

```console
python3 hello.py
python3 welcome_pause.py
python3 classroom_welcome_starter.py
```

On a Windows installation configured with the Python launcher, use:

```console
py hello.py
py welcome_pause.py
py classroom_welcome_starter.py
```

Type only the contents of the source files into an editor. The `>>>` characters
shown in some Python documentation are an interactive prompt, not source code.

For `welcome_pause.py`, the program is waiting—not frozen—when it displays
`Press Enter when you are ready.` Submitting any line lets that run continue;
the example does not yet check what you entered.

`classroom_welcome_starter.py` is the editable starting point for the in-class
exercise. Preserve the original and save your version as `classroom_welcome.py`.
