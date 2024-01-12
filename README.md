# [DRAFT] Software Development Workflow

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
- [Engineering](/pages/workflow/engineering.md)
- [Definitions](/pages/definitions.md)


### Systems

The following links refer to pages with information on how various systems may be used in combination with this workflow,
as well as best-practises and recommendations.

- [Issue Tracking System](/pages/systems/issue-tracking-system.md)
- [Version Control System](/pages/systems/version-control-system.md)


### Misc

- [Coding Standards](/pages/coding-standards.md)




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
