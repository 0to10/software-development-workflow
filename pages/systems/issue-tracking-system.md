# Issue Tracking System

> A system that manages and maintains lists of issues and their statuses


This section outlines the requirements for setting up the _Issue Tracking System_ to be used in combination with this
workflow, as well as some recommendations. While any system may be used with this workflow, ensure that the requirements
set out in this section are met.

The _Issue Tracking System_ must be able to differentiate between 3 types of issue statuses:
- _To-Do_ for issues that are not being worked on
- _In Progress_ for issues that are actively being worked on
- _Done_ for issues that have been completed


## Issue types

Issue types should be refined to fit the responsibilities of a team. You may use the examples below as a starting point
to build out your own.

> Ensure that each issue type is clearly distinguishable from the next, as to limit confusion (time spent) when selecting
> the appropriate issue type for work that needs to be done. Do not introduce more issue types than are needed for a team
> to complete their work.

Note that there is a clear distinction between issue types that deliver value to one or more of your customer(s), and
issue types that primarily have a cost. Epics and Stories deliver value, while all other tasks may be seen as an investment
to achieve that value.

With the above in mind, hours must always be logged on the issue types where work is done, and never on the parent issue
types (such as Epics and Stories).

### Epic
> A deliverable consisting of multiple Stories or Tasks

Epics consist of multiple shippable pieces (Stories, Tasks or Spikes) that share the same end goal. Epics help with
organising and prioritise work, as well as allowing multiple teams to work on a project.  
Epics are often introduced when a Story is too big to deliver in a single sprint, and are written from the perspective
of a user.

### Story
> An end goal written from the perspective of an (end) user

Estimate: `<5 days`

A Story should deliver value to one or more of your customer(s). The work for a Story must be done in subtasks. A Story
delivers value when all subtasks are completed.  
Each subtask may take no longer than 5 hours to complete.

### Defect
> A lack or flaw that causes unintended behavior

Estimate: `1-5 hours`

Defects are separate and distinct work items that are unrelated to items assigned to the current sprint, and do not
prevent any upcoming release(s).

### Task
> An issue that contains everything required to complete a deliverable

Estimate: `1-5 hours`

While Stories fulfill the main object for each sprint, Tasks do work to deliver a Story to the customer. If no dedicated
issue type is made for doing miscellaneous work (chores), a Task may be used as well.

### Spike
> Exploratory work to investigate how an issue should be resolved

Estimate: `~1 day`

Sometimes, especially with larger chunks of work, it may not be clear how an end goal should be met. A Spike is a reservation
of time within a sprint to refine how to meet the objective of an issue, preferably in the most efficient way.  
The outcome of a Spike should be either a plan to deliver the end goal of an issue, or a decision to abandon the work.


## Subtask types

The workflow distinguishes between two types of Subtasks: Generic subtasks that do part of a unit of work, and Bug subtasks
should be raised against an issue for defects found during testing.

### Subtask
> An issue that contains a piece of the work to complete a deliverable

Estimate: `1-5 hours`

A (generic) Subtask contains a piece of the work to complete (part of) a deliverable, and should take no more than 5 hours to complete.

### Bug
> A lack or flaw discovered during testing that causes unintended behavior

Bugs are raised during the QA/testing process, and are the feedback loop from the Deployment process back into the
Engineering process. Bugs may only be raised against an issue when the change is not yet available to customers.

As a general guideline, a Bug should not take longer than 5 hours to complete.


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