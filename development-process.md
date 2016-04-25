#Agile Playbook (Work In Progress)

* Planning
* Process
* Deployment
* Updates
* Deadlines
* Best practices
* Bugs/Defects
* Validating fixes

##Planning

###Daily Meeting
Everyday meeting where team members answer the following questions:

* What did I do yesterday?
* What will I do today?
* Is there anything that prevents me from doing my tasks?

###User Stories
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

Definition of done is decided by the team and may vary per project.

###Acceptance Criteria
List of requirements per user story. Guides to team on how to implement the story by enumerating expected features or requirements that must be done for the story to be accepted by the Product Owner.

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
Demo the shipped code to the entire team with the stakeholders. This provides a tangible component to the team's accomplishment. Since not all features or code changes are visible from the front-end (Web Services, etc), there are times when a mock-up client can be used to demonstrate a feature.

In the context of Continuous Integration (CI), there are instances when a formal Review setup is not practiced especially when the team is closely working with the Product Owner. If the Product Owner has already signed off on the deployment, it can be taken as **accepted**.

###Retrospective
For Scrum there is a clearly defined slot on when the team should do a retrospective.

###Development Guidelines

####Always write tests

####Commit frequently. Avoid huge commits
Large commits make it difficult to revert when a breaking change is merged. Granular commits enable better change visibility.

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
* Critical fixes can be pushed as soon as they are availabe. It should be accompained by its own changelog entry
* Deployment of critical fixes should be approved by a change control board
* Non-critical fixes are deployed on schedule
* Check in frequently
* Do not check in untested code
* Do not check in broken code
* Do not check in when tests are failing

###Changelog
It is equally important to keep an updated changelog enumerating the updates.

Place the changelog in the repo so when the code is merged, the changelog updates are merged as well.

> *Whether the edge changelog is available to the public is something to be discussed*

####Format
Header per entry would follow a date format (DDMMYYY). For the change items, it is in bullet form pulled from the Git commit message of the merged code. It is important to have a single line commit message for the list items to line up legibly.

*Example*
> ##25042016
> * Add login page

For change items specific to an integration, commit message should follow this format

*Example*
> ##25042016
> * ATS name | Add unique ID to API call

##Updates
Effectively managing technical debt by making updates are applied whenever possible.

Breaking changes usually happens when an update is applied to an app that has significant technical debt.

It is recommended practice to ensure update compatiblity whenever available.

Rules in implementing updates:

* Have an automated regression testing
* Have a CI system
* Updates must go through the entire development process

##Deadlines

All deadlines are movable.

It is important not to commit to arbitrary deadlines. The best practice on setting deadlines is to let the backlog speak for itself by measuring the work done from previous cycles to set a benchmark on what the team can accomplish in a given amount of time.

###Fixed Date Projects

In the current business environment it is common to have an agreement on the expected project delivery date to plan out non-development activites (e.g. Marketing campaign). In this scenario, it is recommended that the team would spend time trying to build the product before a timeline is given. This would help the team understand the context of the project and have an **estimate** on the workload required.

##Best Practices

###Style Guide

Using a static code analyzer like [Rubocop](https://github.com/bbatsov/rubocop) to enforce style guide is a good way to get started.

For projects that have a huge code repository, a tool like [Pronto](mmozuras/pronto) where you can run static code analyzers just for the delta is worth considering.

###Acceptance Test

All code commits should have corresponding tests and it should pass.

##Bugs/Defects

Bugs / Defects are also written in user stories

*Example*
> As a user, I DO NOT want to receive more than one (1) email confirmation message

If possible, include steps to reproduce the behaviour.

*Example*
* Register into the website by entering a valid email and password

Bug / Defect user stories should also include an acceptance criteria.

*Example*
* Able to register using a valid email address and password
* Receive only one (1) email confirmation message

*Example*
* Valid email address is accepted into the site
* Only one (1) email confirmation message is sent to the entered email address

##Validating Fixes
To review a fix a 24 hour window or until end of shift next day will be given. If deploy is scheduled on the next day, all fixes should be signed off within the day.

For hotfixes, it should be reviewed as soon as it is available.

##References
* http://blog.aelogica.com/development/aelogica-flavored-agile/
* https://www.thoughtworks.com/continuous-integration
* http://www.joelonsoftware.com/articles/fog0000000043.html
* http://www.payton-consulting.com/how-to-write-user-stories-for-bugs/
