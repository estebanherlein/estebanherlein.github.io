---
title: "Performing code reviews"
categories:
  - Blog
tags:
  - Quality Assurance
  - Software Testing
---


A code review is a synchronization point among different team members and thus has the potential to block progress.

Consequently, code reviews need to be prompt (on the order of hours, not days), and team members and leads need to be aware of the time commitment and prioritize review time accordingly.

If you don’t think you can complete a review in time, please let the committer know right away so they can find someone else.

A review should be thorough enough that the reviewer could explain the change at a reasonable level of detail to another developer. This ensures that the details of the code base are known to more than a single person.

As a reviewer, it is your responsibility to enforce coding standards and keep the quality bar up. Reviewing code is more of an art than a science. 

The only way to learn it is to do it; an experienced reviewer should consider putting other less experienced reviewers on their changes and have them do a review first. 

Assuming the author has followed the guidelines above (especially with respect to self-review and ensuring the code runs), here’s an list of things a reviewer should pay attention to in a code review:


<h2>Purpose</h2>

Does this code accomplish the author’s purpose? 

Every change should have a specific reason (new feature, refactor, bugfix, etc). 

Does the submitted code actually accomplish this purpose?

Ask questions. Functions and classes should exist for a reason. When the reason is not clear to the reviewer, this may be an indication that the code needs to be rewritten or supported with comments or tests.

<h2>Implementation</h2>

Think about how you would have solved the problem.

If it’s different, why is that? Does your code handle more (edge) cases? Is it shorter/easier/cleaner/faster/safer yet functionally equivalent? Is there some underlying pattern you spotted that isn’t captured by the current code?

Do you see potential for useful abstractions? 

Partially duplicated code often indicates that a more abstract or general piece of functionality can be extracted and then reused in different contexts.

Think like an adversary, but be nice about it. Try to “catch” authors taking shortcuts or missing cases by coming up with problematic configurations/input data that breaks their code.

Think about libraries or existing product code. 

When someone re-implements existing functionality, more often than not it’s simply because they don’t know it already exists. Sometimes, code or functionality is duplicated on purpose, e.g., in order to avoid dependencies. In such cases, a code comment can clarify the intent. Is the introduced functionality already provided by an existing library?

Does the change follow standard patterns? 

Established code bases often exhibit patterns around naming conventions, program logic decomposition, data type definitions, etc. It is usually desirable that changes are implemented in accordance with existing patterns.

Does the change add compile-time or run-time dependencies (especially between sub-projects)?

We want to keep our products loosely coupled, with as few dependencies as possible. Changes to dependencies and the build system should be scrutinized heavily.

<h2>Legibility and style</h2>

Think about your reading experience. 

Did you grasp the concepts in a reasonable amount of time? Was the flow sane and were variable and methods names easy to follow? Were you able to keep track through multiple files or functions? Were you put off by inconsistent naming?

Does the code adhere to coding guidelines and code style? 

Is the code consistent with the project in terms of style, API conventions, etc.? As mentioned above, we prefer to settle style debates with automated tooling.

Does this code have TODOs? TODOs just pile up in code, and become stale over time. Have the author submit a ticket on GitHub Issues or JIRA and attach the issue number to the TODO. The proposed code change should not contain commented-out code.

<h2>Maintainability</h2>

Read the tests. If there are no tests and there should be, ask the author to write some.

Truly untestable features are rare, while untested implementations of features are unfortunately common. 

Check the tests themselves: are they covering interesting cases? Are they readable? Does the CR lower overall test coverage? Think of ways this code could break. Style standards for tests are often different than core code, but still important.

Does this CR introduce the risk of breaking test code, staging stacks, or integrations tests? These are often not checked as part of the pre-commit/merge checks, but having them go down is painful for everyone. Specific things to look for are: removal of test utilities or modes, changes in configuration, and changes in artifact layout/structure.

Does this change break backward compatibility? If so, is it OK to merge the change at this point or should it be pushed into a later release? Breaks can include database or schema changes, public API changes, user workflow changes, etc.

Does this code need integration tests? Sometimes, code can’t be adequately tested with unit tests alone, especially if the code interacts with outside systems or configuration.

Leave feedback on code-level documentation, comments, and commit messages. Redundant comments clutter the code, and terse commit messages mystify future contributors. This isn’t always applicable, but quality comments and commit messages will pay for themselves down the line. (Think of a time you saw an excellent, or truly terrible, commit message or comment.)

Was the external documentation updated? If your project maintains a README, CHANGELOG, or other documentation, was it updated to reflect the changes? Outdated documentation can be more confusing than none, and it will be more costly to fix it in the future than to update it now.

Don’t forget to praise concise/readable/efficient/elegant code. Conversely, declining or disapproving a CR is not rude. If the change is redundant or irrelevant, decline it with an explanation. If you consider it unacceptable due to one or more fatal flaws, disapprove it, again with an explanation. Sometimes the right outcome of a CR is “let’s do this a totally different way” or even “let’s not do this at all.”

Be respectful to the reviewees. While adversarial thinking is handy, it’s not your feature and you can’t make all the decisions. If you can’t come to an agreement with your reviewee with the code as is, switch to real-time communication or seek a third opinion.

<h2>Security</h2>

Verify that API endpoints perform appropriate authorization and authentication consistent with the rest of the code base. Check for other common weaknesses, e.g., weak configuration, malicious user input, missing log events, etc. When in doubt, refer the CR to an application security expert.


<h2>Comments: concise, friendly, actionable</h2>

Reviews should be concise and written in neutral language. Critique the code, not the author. When something is unclear, ask for clarification rather than assuming ignorance. Avoid possessive pronouns, in particular in conjunction with evaluations: “my code worked before your change”, “your method has a bug”, etc. Avoid absolute judgements: “this can never work”, “the result is always wrong”.

Try to differentiate between suggestions (e.g., “Suggestion: extract method to improve legibility”), required changes (e.g., “Add @Override”), and points that need discussion or clarification (e.g., “Is this really the correct behavior? If so, please add a comment explaining the logic.”). Consider providing links or pointers to in-depth explanations of a problem.

When you’re done with a code review, indicate to what extent you expect the author to respond to your comments and whether you would like to re-review the CR after the changes have been implemented (e.g., “Feel free to merge after responding to the few minor suggestions” vs. “Please consider my suggestions and let me know when I can take another look.”).