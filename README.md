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
  - [Estimations and velocity](/pages/workflow/engineering/estimations-and-velocity.md)
  - [Identifying scope-creep](/pages/workflow/engineering/identifying-scope-creep.md)
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
