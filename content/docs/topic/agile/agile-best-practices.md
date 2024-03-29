---
title: Agile Best Practices
bookToC: 2
bookHidden: true
---
# Agile Best Practices

## Sprint Planning

How to ensure team has selected a group of stories to ensure delivering value to the company.

### Lock Requirements

During a sprint or iteration no changes be made that would affect the sprint goal:

Changes mid-sprint jeopardizes investments made into the work.

- Planning/re-planning isn't free
- The discarded work took time/resources

Increased Risk.

- Other features might get derailed/not delivered

### Time-Boxing

The duration of each sprint should be short and consistent (usually between 2-4 weeks). This simplifies planning and allow a cons_tent rhythm to be established. Let stories drop if time runs out for a sprint.

- Makes planning easier
- A fixed and known end-date lends a sense of focus and urgency.
- Prevents feature creep

### Only the Team Estimates

The Development Team should be estimating the efforts involved.

- They have unique insights into the obstacles that may arise
- Estimates can reveal incorrect assumptions about requirements

### Product Owner Availability

Keep Product Owner available to answer questions from the team. They are the expert on what features needs to be implemented, and in what order:

- They have unique domain knowledge in case of needed clarification
- Needed during estimation of timeframe and goals
- Stories will initially lack the details needed for implementation

## User Feedback

### Demo Every Sprint

Long-winded progress reports can be easily misinterpreted.

Stakeholders need to see the product as early as possible:

- They don't have time to read detailed specs
- Software offers clearer picture than specs, allows for better planning
- Better planning means less wasted work

### Make feedback easy

Users are busy. But we need them.

- Making feedback difficult means issues will slip through
- Making feedback easy will boost product quality
- Read feedbacks out loud. In meetings
- Good feedback boosts morale. Negative feedbacks offers rooms to improve

## Testing

Ensure technical debt isn't accruing on project.

### Test at Development Time

Testing is far more effective in tandem with development. Bugs are harder to find after development than during.

If testers are at capacity, developers should step in and help them test

Untested code is a dangerous technical debt.

- Lower velocity
- Compounding defect
- Rising support times

### Shared Definition of Done

Definition: A list of all the tasks that must be completed before a feature is considered complete.

When an item is declared as done, it must be potentially releasable in that state.

- Avoids miscommunication
- Keeps testing from slipping through

## Test-Driven Development

Write tests first. Then code. And those tests drives the development.

Tenets of TDD:

- code is written only when there is a failing test that requires the code to pass
- the bare minimum amount of code is written to ensure that the test passes
- duplication is removed at every step
- once all test are passing, the next failing test is added for the next required functionality

The tenets ensures:

- code develops organically, and that every line of code is purposeful
- code remains highly modular, cohesive and reusable (as you need to be able to test it)
- a comprehensive array of tests to prevent future breakages and bugs
- the tests also act as specification, and thus documentation for future needs and changes

When writing a test, ask yourself:

- What are you testing?
- What should it do?
- What is the actual output?
- What is the expected output?
- How can the test be reproduced?

Summary:

For each test written ask yourself

- What component aspect are you testing?
- What is the actual output?
- What is the expected output?
- What is the expected output?
- What should the feature do?
