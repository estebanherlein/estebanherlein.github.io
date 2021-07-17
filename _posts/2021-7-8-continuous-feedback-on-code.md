---
title: "Continuous Feedback on Code"
categories:
  - Blog
tags:
  - Software Testing
  - Bug Hunting
  - Teaching
  - Quality Assurance
---

<h2>Review fewer than 400 lines of code at a time. </h2>

The brain can only effectively process so much information at a time; beyond 400 LOC, the ability to find defects diminishes.

In practice, a review of 200-400 LOC over 60 to 90 minutes should yield 70-90% defect discovery. So, if 10 defects existed in the code, a properly conducted review would find between seven and nine of them.

<h2>Do not review for more than 60 minutes at a time</h2>

Just as you shouldn´t review code too quickly, you also should not review for too long in one sitting. When people engage in any activity requiring concentrated effort over a period of time, performance starts dropping off after about 60 minutes. Studies show that taking breaks from a task over a period of time can greatly improve quality of work. Conducting more frequent reviews should reduce the need to ever have to conduct a review of this length.

<h2>Foster a positive code review culture</h2>

Peer review can put strain on interpersonal team relationships. It´s difficult to have every piece of work critiqued by peers and to have management evaluating and measuring defect density in your code. Therefore, in order for peer code review to be successful, it´s extremely important that mangers create a culture of collaboration and learning in peer review.

While it´s easy to see defects as purely negative, each bug is actually an opportunity for the team to improve code quality. Peer review also allows junior team members to learn from senior leaders and for even the most experienced programmers to break bad habits.

<h2>Embrace the subconscious implications of peer review</h2>

The knowledge that others will be examining their work naturally drives people to produce a better product. This "Ego Effect" naturally incentivizes developers to write cleaner code because their peers will certainly see it. If your code has a 1-in-3 chance of being called out for review, that´s enough of an incentive to double-check your work.

<h2>Use checklists</h2>

It´s very likely that each person on your team makes the same 10 mistakes over and over. Omissions in particular are the hardest defects to find because it´s difficult to review something that isn´t there. Checklists are the most effective way to eliminate frequently made errors and to combat the challenges of omission finding. Code review checklists also provide team members with clear expectations for each type of review and can be helpful to track for reporting and process improvement purposes.
