#Agile Playbook

* Planning
* Process
* Deployment
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

Kanban guidelines:

* Visualize workflow
* Define Work In Progress (WIP) limit
* Define a limit per Kanban column
* Define a sizing metric
	* e.g. T-shirt sizes

Scrum guidelines:

* Define sprint duration
* Define sizing metric
	* e.g. Planning poker cards, etc

##Deployment

###Continuous Integration
Development practice that requires developers to integrate their code into a shared repository frequently (once a day or several times a day).

###Daily updates
Pushing updates daily minimizes possible integration issues and backtracking effort if the build breaks.

###Changelog
It is equally important to keep an updated changelog enumerating the updates.

Place the changelog in the repo so when the code is merged the changelog updates are merged as well.

*Whether the edge changelog is available to the update is something to be discussed*

##Deadlines

All deadlines are movable.

It is important no to commit to arbitray deadlines. The best practice to setting deadline is to let the backlog speak for itself. Measuring the work done from previous cycles to set the benchmark on what the team can accomplish in a given amount of time.

###Fixed Date Projects

In the current business environment it is common to have an agreement on the expected project delivery date to plan out non-development activites (e.g. Marketing campaign). In this scenario, it is recommended that the team would spend time trying to build the product before a timeline is given. This would help the team understand the context of the project and have an **estimate** on the workload require.

##Best Practices

###Style Guide

Using a static code analyzer like Rubocop to enforce style guide is a good way to get started.

For projects who have a huge code repository, a tool like [Pronto](mmozuras/pronto) where you can run static code analyzers just for the delta is worth considering.

###Unit Testing

