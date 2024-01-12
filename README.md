# [DRAFT] Simple Software Development Workflow

Whether you are part of a large organisation that employs thousands, or a small group within a startup, developing high
quality software is always on our mind. With many different stakeholders in every project, the checklist to get software
to the end-user seems to be growing every other week, and so keeping focus is key.

Decades of experience in software development has taught us a great deal about building software. We've put all of our
learnings into a simple process that helps to keep focus on the work, requires active collaboration between team members
and improves quality of the delivered software.

Many of the concepts and details of this workflow are based on other ideas, best-practises and studies, combined with
hands-on experience. The workflow incorporates ideas from Extreme Programming, Intent-Based Leadership (IBL), personality
and team composition studies, Domain Driven Design (DDD), and much more, but is in no way a replacement of studying those
yourself and building your own workflow or process.


## Getting Started

> It is recommended to only use this workflow when the team...
> - consists of at least 4 software engineers
> - has agreed on how to measure success
> - uses hours for estimations (not story points)
> - agrees to commit to this workflow


### The Workflow

- [Refinement](/pages/workflow/refinement.md)
- [Definitions](/pages/definitions.md)

### Systems

The following links refer to pages with information on how various systems may be used in combination with this workflow,
as well as best-practises and recommendations.

- [Issue Tracking System](/pages/systems/issue-tracking-system.md)
- [Version Control System](/pages/systems/version-control-system.md)

### Misc

- [Coding Standards](/pages/coding-standards.md)





## Understandings

This software development workflow is limited to the development of software,
and does not cover anything related to deployment of the software, nor does it
take into account refinement of the work.

A templated software development workflow may be a good start for your business
but feel free to experiment and try variants or combinations of different ways
of working.


## Schematic overview

The schema below provides an overview of this software development workflow:

```mermaid
sequenceDiagram
    To Do->>In Progress: Software Engineer starts work and<br>transitions task to "In Progress"

    In Progress->>Pending Review: Software Engineer moves task to<br>"Pending Review" when work is completed

    In Progress-->>To Do: Software Engineer moves the task back to "To Do"
    Note right of To Do: Anyone should be able to move a task<br>back if the deliverable is not understood

    Pending Review->>In Review: Reviewer moves the task to<br>"In Review" to start the peer-review
    Note right of Pending Review: Reviewer validates the work<br>using the acceptance criteria

    In Review->>Done: Reviewer moves the task to "Done" when<br>the acceptance criteria are met

    In Review-->>In Progress: Reviewer moves the task back to "In Progess"<br>when the acceptance criteria are not met
    Note right of In Progress: The original Software Engineer is<br>reassigned to the task    
```


## The workflow in detail

The summary below gives detailed insight into each of the states used in the
software development workflow.

Although some organisations may need to deviate in some of the areas, mostly
because of resource constraints, please be aware that separation of duties when
implementing this workflow are aimed to improve sharing of knowledge within a
team, and ensure agreed upon quality standards are met.

Some management systems, such as ISO 27001 and 9001, will require some of these
practises to be thought of and/or in place within your organisation.

Always ensure that separation of duties within any workflow is enforced within
the issue and/or project tracking system of your choice.


### To Do

> The "To-Do" state indicates that an issue is ready to be worked on. Any
> software engineer should be able to work on these issues

To ensure that any software engineer within the team is able to start work on a
task, it is important to have a proper description of what the desired goal of
that task is. Tasks that do not have a clear and understandable description of
what the deliverable is, should not be in the "To Do" state.

Organisations may vary on how the deliverable is described for a task, and many
teams have different preferences on what works for them. Generally speaking it
works well to have some background information on why specific work should be
done, what the desired implementation is to meet a certain demand and what the
benefit is of completing the work.

Although teams may differ in their approach to capture the requirements for a
task, it's generally a good practise to keep any description short and to the
point. Checklists may work very well for some teams.

While a task is in the "To Do" state it is not assigned to anyone.


### In Progress

> The "In Progress" state indicates that an issue is currently being worked on.
> Issues in this state must be assigned to a software engineer

The software engineer should follow the development procedure that was agreed
upon by the whole team. The development procedure should provide guidelines on
coding standards, test requirements and general best practises.

A software engineer could discover impediments when working on a task. While
most of these impediments may be resolved within a reasonable amount of time,
and resolving those impediments may not affect the estimation (by much), there
should be a possibility for a software engineer to directly transition a task
back to "To Do" or "Done". In the latter case, the software engineer should
apply a resolution like "Abandoned" with an explanation.

Valid reasons of moving a task back or directly to "Done" are:
- During development the software engineer spots an issue in the affected code
  that will exceed the estimate by more than is reasonable
- The desired outcome of the task, while in development, is incomplete and must
  be refined (again) to ensure everyone is aligned on the deliverable

Transitioning a task from this state to "To Do" or "Done" is a deviation of the
workflow and must be escalated to the other team members.


### Pending Review

> The "Pending Review" state indicates that an issue is ready to be reviewed.
> Any software engineer, except the person who did the initial work on the
> issue, should be able to review it

Similar to the "To Do" state, the "Pending Review" state indicates that a task
is ready to be worked on. The initial work on the task is done, and before the
task is moved to "Done" someone else should review the work to ensure that the
developed work satisfies all agreed upon criteria.

During this state the work is not assigned to anyone.


### In Review

> The "In Review" state indicates that an issue is currently being reviewed.
> Issues in this state must be assigned to a software engineer

During the "In Review" state the Reviewer validates that the work meets all
agreed upon criteria. The Reviewer must provide comments in the version control
system for any criteria that were not met. These comments must be passed to the
original software engineer.

If there are any comments on the task, the Reviewer will transition the task
back to "In Progress" and assign the original software engineer.

To ensure quality it is most important to ensure that it is not possible for
any software engineer to review their own work. While some organisations may
have a dedicated role for quality assurance, smaller organisations may choose
to have this responsibility shared by people with the same role.


### Done

> The "Done" state indicates that (engineering) work on an issue has been
> completed, and that the work meets all agreed upon acceptance and coding
> criteria

When the Reviewer has ensured that the task has been completed in accordance
with the criteria that were agreed upon, the task must be moved to "Done".

Tasks moved to this state must be unassigned.

Although development work on the task has been completed, and peer-review has
not discovered any missed acceptance criteria, there may be other work that
must be done on the task to complete the work as a whole. "Done" within this
workflow means that the software engineering work has been completed.

Tasks in the "Done" state may be the starting state for any other related
workflows, like a deployment pipeline.


## Reviewing

The peer-review process ensures that quality standards are met for every change
to the software, but if not done correctly it could result into a lot of spent
time without any concrete benefits.

To keep up productivity while guarding quality, consider the review process a
collaboration between the original software engineer and a Reviewer. The people
involved for a single task should not change, and the team should be aware of
who are responsible for the delivery of a task.

For the first review the Reviewer must provide comments to the software in the
version control system. The original software engineer will aim to resolve any
comments made by the Reviewer, after the Reviewer has transitioned the task
back to "In Progress" and reassigned the original software engineer. When all
the comments have been resolved, the task is transitioned according to the
workflow - as described above.

The Reviewer should watch for any tasks that are transitioned to the "Pending
Review" state that the Reviewer previously reviewed. These tasks should be
reviewed again by the same Reviewer.

If any issues are found during the second review, the Reviewer should consider
working directly together with the original software engineer to resolve any
remaining issues.


## Estimations and velocity

As defined in the Definitions section (see above), it should be possible to
complete work on a task within 5 hours. Most companies have working days of 8
hours, which means that most tasks can be finished within a single working day.

Software engineering frequently requires making modifications to many different
parts of a software application. There may be people in your team that thrive
on elaborate changes, but for others it might be daunting. If work is left in
an unfinished state at the end of a working day, the software engineering that
is working on the task will need to read into the changes the next day. This
takes time, and increases the change of making mistakes.

Tasks that exceed the desired 5-hour limit should be split up. Deliverables
that need to be split up should be combined into a story.


## Identifying scope-creep

It's common for some details to be forgotten or overlooked during refinement of
tasks for a sprint. Not responding on time to tasks that are not well-defined
may  result in a failure to deliver the work that was committed to, because
tasks take more time to complete or scope is silently increased. Mitigating
this risk requires an understanding of what the work _should_ look like, and
knowing what to do if the work deviates from what was expected.

Each team _must_ agree on a set of questions to determine the expectancy of the
work for each type of work.

### Examples of questions for software development

Below are a number of questions that _may_ be used to determine the expected
work for software development tasks:

- Which areas of the software application do you expect to be working on?
- Which other components / areas of the software application are related to the
  area you are expecting to work on?
- Are you expecting to primarily add, change or delete code?
- What is the coverage level of the code you are expecting to work on?
- Do you understand the purpose / business logic of the requested change?
- Are there any other pending tasks that will make changes to the same parts of
  the software application?
- Do I know who to reach out to if I come across any blockers[^1]?

### Before starting work

Before commencing with any work the agreed upon questions must be answered to
understand the expected effort involved to complete the work. During the first
iterations of experimenting with this approach, the more senior members within
the team must support more junior members.

### Dealing with misunderstood work

Any deviation from the expected work must be discussed with the team. When or
where deviations are discussed may differ between teams, however:

- where deviations are discussed must be accessible throughout the day
- questions regarding misunderstood work must be answered within 1 hour[^2]
- a history of decisions regarding misunderstood work must be maintained
- all decisions from a sprint must be discussed during a retrospective





[^1]: A blocker does not have to be technical, be sure to have people to
reach out to with any type of blocker.
[^2]: Teams may decide on another period but must agree on this with the rest
of the organisation.
