# Version Control System

> A system that tracks changes to a file or a set of files over time


## Repositories

Each individual software application, that can either run standalone or (like libraries) can be used within one or more
other projects, should have its own repository. A repository must contain the source code of the software application, as
well as any automated unit, integration and functional tests.

In some cases it may be desirable to include end-to-end tests within the same repository as the software application, but
this is not a strict requirement.

In organisations with many (dozens) of repositories, organising those repositories in a maintainable way is essential.
Repositories should not be organised based on:
- who, what, or which team is responsible for it
- functional similarities, such as grouping all microservices or libraries

Information on how a software application is built should be kept, preferably scripted, as part of the same code
repository. Portions of how a software application is deployed may in some cases also be included in the same repository,
with the strict requirement that it information on where the software application is deployed is not included.

For various reasons it should not matter to the software application where it is deployed to. You may have a requirement
to deploy the same software application to multiple geographic regions. Ideally the software application does not have to
change for it to be deployed to different environments, instead it should modify behavioural specifics using
configuration (such as the debugging verbosity).


## Default branches

The _Version Control System_ should provide dedicated branches for a) fixing escaped defects, and b) feature development.
These branches must be called `main` and `develop` respectively.

Default branches must be protected against accidental deletion and must deny history rewrites.

| Name    | Description                                                                             |
|:--------|:----------------------------------------------------------------------------------------|
| main    | Branch containing the latest stable version of the software application                 |
| develop | Branch containing a version of the software application that is still under development |

The separation of responsibilities between the `main` and `develop` branches should be used by the _Software Engineers_
to plan changes to the software application. Changes that will likely require more testing should not be made to a branch
that must remain as closely as possible to what is currently in a production environment, as to not block or
overcomplicate resolving escaped defects.


## Branch naming

Branch names must be based on the combination of the target branch name and the issue number, separated by an underscore.
Only issues that will be worked on by the Engineering team, including their subtasks, must be part of a branch name.

Epics are mostly used from a project management perspective, and are never directly worked on. Their issue number must
therefor not be part of a branch name.

Given an Epic with issue number `OSS-15`, a Story with issue number `OSS-22` and a Subtask with issue number `OSS-99`, the
branch name must be: `main_OSS-22_OSS-99`.


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
change, such as `Formatting.`, `Refactored: <explanation>.`, etc.