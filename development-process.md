#Agile Playbook

* Planning
* Process
* Deployment
* Updates
* Deadlines
* Best Practices

##Planning

###Daily Meeting
Everyday meeting where team members answer the following questions:

* What did I do yesterday?
* What will I do today?
* Anything that prevents me from doing my tasks?

###Tasks
Tasks are expressed as user stories. The goal is to move all the task items from left to right.

*Example*
> As a candidate, I want to be able to record my video interview from the browser

###Definition of Done
List of requirements that must be true for each task for it to be considered as done. This helps remove ambiguity and what is considered to be done.

*Example*
> * Code conforms to style guide
> * Code unit tested
> * Task item updated
> * Pushed to staging

Definition of done is decide by the team and may vary per project.

###Acceptance Criteria
List of requirements per user story. Guides to team on how to implement the story by enumerating expected features or requirements that has to be done for the story to be accepted by the Product Owner.

*Example*
> User story: As a customer, I want to be able to register into the site.
> 
> Acceptance criteria:
>
> * A customer can enter their email address and password to register
> * Captcha for spamming requests
> * Email format validation
> * Unique email address validation
> * Customer will receive a confirmation email

##Process

Kanban checklist:

* Visualize workflow
* Define Work In Progress (WIP) limit
* Define a limit per Kanban column
* Define a sizing metric
	* e.g. T-shirt sizes

Scrum checklist:

* Define sprint duration
* Define sizing metric
	* e.g. Planning poker cards, etc
* Ritual schedule

###Backlog Grooming
Regularly spend time to improve your Backlog for better clarity, prioritization or structuring.

###Review
Demo the shipped code to the entire team with the stakeholders. This provides a tangible component to the team's accomplishment. Since not all features or code changes are visible from the front-end (Web Services, etc), there are times where a mock-up client can be used to demonstrate a feature.

In the context of Continuous Integration (CI), there are instances where a formal Review setup is not practiced especially when the team is closely working with the Product Owner. If the Product Owner has already signed off on the deployment it can be taken as **accepted**.

###Retrospective
For Scrum there is a clearly defined slot on when should the team do a spri

###Development Guidelines

####Always write tests

####Commit frequently. Avoid huge commits
Large commits make it difficult to revert when a breaking change is merged. Granular commits enable better change visibility

####Do not re-open or change accepted stories
Create a new story with any changes that come up after a story has been accepted.

####Fix bugs before writing new code
The longer a bug is in the system, the more expensive it is to fix.

As you are pushing in new features with

##Deployment

###Continuous Integration
Development practice that requires developers to integrate their code into a shared repository frequently (once a day or several times a day).

###Daily updates
Pushing updates daily minimizes possible integration issues and backtracking effort if the build breaks.

####Rules in pushing to CI
* Explicit timeslot when to push updates to production
* Critical fixes can be pushed as soon as they are availabe. Should be accompained by its own changelog entry
* Deployment of critical fixes should be approved by a change control board
* Non-critical fixes are deployed on schedule
* Check in frequently
* Do not check in untested code
* Do not check in broken code
* Do not check in when tests are failing

###Changelog
It is equally important to keep an updated changelog enumerating the updates.

Place the changelog in the repo so when the code is merged the changelog updates are merged as well.

> *Whether the edge changelog is available to the public is something to be discussed*

##Updates

Effectively managing technical debt by making updates are applied whenever possible.

Breaking changes usually happens when an updated is applied to an app that has significant technical debt.

It is a recommended practice to ensure update compatiblity whenever it is available.

Rules in implementing updates:

* Have an automated regression testing
* Have a CI system
* Updates must go through the entire development process

##Deadlines

All deadlines are movable.

It is important no to commit to arbitray deadlines. The best practice to setting deadline is to let the backlog speak for itself. Measuring the work done from previous cycles to set the benchmark on what the team can accomplish in a given amount of time.

###Fixed Date Projects

In the current business environment it is common to have an agreement on the expected project delivery date to plan out non-development activites (e.g. Marketing campaign). In this scenario, it is recommended that the team would spend time trying to build the product before a timeline is given. This would help the team understand the context of the project and have an **estimate** on the workload require.

##Best Practices

###Style Guide

Using a static code analyzer like [Rubocop](https://github.com/bbatsov/rubocop) to enforce style guide is a good way to get started.

For projects who have a huge code repository, a tool like [Pronto](mmozuras/pronto) where you can run static code analyzers just for the delta is worth considering.

###Acceptance Test

All code commits should have corresponding tests and it should pass.

##References
* http://blog.aelogica.com/development/aelogica-flavored-agile/
* https://www.thoughtworks.com/continuous-integration
* http://www.joelonsoftware.com/articles/fog0000000043.html
