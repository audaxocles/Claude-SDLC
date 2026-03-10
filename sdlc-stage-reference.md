# SDLC Stage Reference Sheet

Quick-reference for every stage of our Kanban-based SDLC: what goes in, who acts, what triggers the work, and what comes out.


## Backlog

| | Detail |
|---|---|
| **Inputs** | Feature requests, bug reports, stakeholder feedback, technical debt items, analytics insights |
| **Processed by** | Product Owner |
| **Trigger** | New request submitted, replenishment meeting identifies a gap, or stakeholder raises a need |
| **Outputs** | Prioritised backlog item with title, description, and rough business value ranking |


## Ready (Refinement)

| | Detail |
|---|---|
| **Inputs** | Prioritised backlog item |
| **Processed by** | Product Owner + Development Team (collaborative refinement) |
| **Trigger** | Ready column drops below its WIP limit (5 items) during the weekly replenishment meeting |
| **Outputs** | Refined card with clear acceptance criteria, size estimate (S/M/L), identified dependencies, and any supporting design assets or technical notes |


## In Progress (Development)

| | Detail |
|---|---|
| **Inputs** | Refined card from the Ready column |
| **Processed by** | Developer (self-assigned by pulling from Ready) |
| **Trigger** | Developer has capacity (within personal WIP limit of 3) and pulls the highest-priority Ready item |
| **Outputs** | Working code on a feature branch, unit tests passing locally, and a pull request opened against the main branch |


## Code Review

| | Detail |
|---|---|
| **Inputs** | Open pull request with passing CI checks |
| **Processed by** | Peer reviewer (another developer on the team) |
| **Trigger** | Pull request is opened or moved into the Code Review column; reviewer picks it up when they have capacity |
| **Outputs** | Approved pull request (or feedback requiring changes), review comments resolved, code merged to main branch |


## Testing / QA

| | Detail |
|---|---|
| **Inputs** | Merged code on main branch, acceptance criteria from the card |
| **Processed by** | QA Engineer or Developer (depending on team structure) |
| **Trigger** | Code is merged to main and a build is deployed to the staging/QA environment |
| **Outputs** | Test results (pass or fail with defect details), verified acceptance criteria checklist, regression confirmation |


## Done (Deployment & Validation)

| | Detail |
|---|---|
| **Inputs** | QA-verified build, deployment checklist |
| **Processed by** | Developer or DevOps (deployment), Product Owner (validation) |
| **Trigger** | All acceptance criteria verified in QA; no open defects on the card |
| **Outputs** | Production deployment, updated release notes, closed card, stakeholder notification |


## Stage Flow Summary

```
Backlog ──▶ Ready ──▶ In Progress ──▶ Code Review ──▶ Testing/QA ──▶ Done
  PO        PO+Team     Developer       Reviewer        QA/Dev       DevOps/PO
```

## Feedback Loops

Cards can move backwards in two scenarios. A code review that requests significant changes sends the card back to In Progress. A QA failure with a defect also returns the card to In Progress. In both cases the card keeps its original priority position and does not re-enter the Ready queue.
