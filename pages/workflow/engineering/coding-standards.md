# Coding Standards

The following coding standards may serve as an example when setting up standards for a team. Note that there are many
read-to-use coding standards, that may be adopted - even if slightly edited - by a team.

> Always ensure that a standard is widely adopted before using it for you team.


## Best Practises

- All changed code (in a commit) is owned by the Software Engineer that made the change
  - Do not apply any auto-formatting to otherwise unchanged code
- Prefer usage of custom Exception classes
- Structure code (files, classes, etc.) according to its place in the domain model
- Do not overly comment the code
- Any strict mode for a language and/or file should be enabled and enforced
- Apply a type declaration whenever possible
- Avoid compound expressions
- Avoid ternary statements


## Naming Conventions

- Class, method and function names must communicate what their intended purpose is
- Classes must be in `PascalCase`, variables (and property names) must be in `camelCase`
- Abbreviation of variable names is not allowed, except in the following cases:
  - Usage of abbreviations used in the domain model (such as "DNS") is permitted
  - Usage of `i` (index) and `l` (length) are permitted in for-loops


## Logging

Many applications implement some level of plain-text logging. Adhere to the following when writing plain-text log lines
to keep searching through, and aggregating log files simple.

- Use a format/template based function or method that supports format placeholders
- Placeholders that will be replaced with text should be surrounded with `"` double quotes
- Avoid mixing single and double quotes in a single log line
- Abbreviated words (such as _can't_ or _couldn't_) should not be used
