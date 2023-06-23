# Version Control System

> A system that tracks changes to a file or a set of files over time


## Default branches

The _Version Control System_ must provide dedicated branches for a) bug fixes, and b) feature development. These
branches must be called main and develop respectively.

| Name	   | Description                                                                             |
|:--------|:----------------------------------------------------------------------------------------|
| main    | Branch containing the latest stable version of the software application                 |
| develop | Branch containing a version of the software application that is still under development |

These branches must be protected against accidental deletion and prevent history rewrites.


## Branch naming

Branch names must be based on the combination of the target branch name and the issue number, separated by an
underscore. The branch name for a bug fix with issue number OSS-10 would be `main_OSS-10`.


## Commit messages

Commit messages must always start with the issue number and a colon, and end with a `.` dot.

Keeping the commit messages in a constant format with specific information, ensures that related changes can be
identified quickly, as well as allowing code changes to be manually linked to issues in the _Issue Tracking System_, in
the event that automatic linking fails.

Example of a commit message while working on an issue:
```
OSS-10: Added a calculator class to add two numbers.
```

Example of a merge commit message:
```
OSS-10: As a user I want to be able to add two numbers.
```

Commits unrelated to the units of work may differ from the conventions above, as long as they indicate the intent of a
change, such as Formatting., Refactored: <explanation>., etc.