# Issue Tracking System

> A system that manages and maintains lists of issues (epics, stories, tasks,
> etc) and their statuses

This section outlines the requirements for setting up the _Issue Tracking System_ to be used in
combination with this workflow, as well as some recommendations. While any system may be used with
this workflow, ensure that the requirements set out in this section are met.

The _Issue Tracking System_ must be able to differentiate between 3 types of issue statuses:
- _To-Do_ for issues that are not being worked on
- _In Progress_ for issues that are actively being worked on
- _Done_ for issues that have been completed


<!--
## Roles

TODO
-->


## Board settings

The development for the engineering team must be kept simple. The schema below contains an overview
of the columns that must be present on the (sprint) board.

![Overview of the required board columns](/assets/images/board-columns.png)

Cards on the board must display (at least) the following information:
- the summary (or title) of the issue
- the current assignee of the issue
- the amount of time the issue has been in a status
- the remaining estimate of the issue


## Automation recommendations

> Any mandatory actions that are not part of the primary duties of a person
> should be automated.

The primary job of a _Software Engineer_ is solving problems and making code modifications, keeping
track of the hours spent on a task - although important and/or required - is not part of their
primary job.

> When selecting actions to automate, consider which system has the most
> knowledge on the topic.

A checklist item to indicate that an issue has sufficient code coverage, may be used to prevent an
issue from transitioning forward, if left unchecked. However, a quality guard as part of a
CI-pipeline will provide more accurate results, and can block a code change from being merged just as
easy.

- Issues that are transitioned to _In Progress_ should be assigned to the current user

- Issues that are transitioned from _In Review_ to _In Progress_ should show a screen to reassign the issue

- Issues that are transitioned to _Pending Review_ should be unassigned, and should show a screen to:
  - log work (hours)
  - add a comment to an issue

- Issues that are transitioned to Done should show a screen to:
  - log work (hours)
  - add a comment to an issue
  - set or update the fix version of an issue
  - set or update the resolution of an issue

- Issues should not be allowed to transition to another state if mandatory actions have not been completed