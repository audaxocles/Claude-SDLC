# Kanban-Based Agile SDLC

## Overview

This document defines our software development lifecycle using a Kanban methodology. The goal is to maintain a continuous flow of work, limit work in progress, and deliver value incrementally without the fixed cadence of sprints.


## Board Columns

Our Kanban board consists of six columns. Each card moves left to right through these stages.

| Column | WIP Limit | Owner | Purpose |
|---|---|---|---|
| Backlog | None | Product Owner | Prioritised list of upcoming work items |
| Ready | 5 | Product Owner | Refined items with clear acceptance criteria, ready to be pulled |
| In Progress | 3 per dev | Developer | Actively being developed |
| Code Review | 3 | Reviewer | Pull request submitted, awaiting peer review |
| Testing / QA | 4 | QA / Developer | Verification against acceptance criteria |
| Done | None | Team | Deployed (or ready to deploy) and validated |


## Workflow Policies

**Pulling work.** Team members pull the highest-priority item from Ready when they have capacity. Never push work onto someone else.

**WIP limits are firm.** If a column is at its limit, the team must resolve the bottleneck before pulling new work. This surfaces problems early rather than hiding them behind a growing backlog.

**Blocking and flagging.** If a card is blocked, mark it with a red flag and note the reason. Blocked items should be discussed at the next standup or escalated immediately if urgent.

**Card structure.** Every card should contain a title, a brief description, acceptance criteria, an assignee (once pulled), and a size estimate (S / M / L).


## Definitions

**Definition of Ready** — an item can enter the Ready column when it has a clear description and acceptance criteria, all dependencies are identified and resolved (or planned for), and the team has estimated its size.

**Definition of Done** — an item moves to Done when the code is merged to the main branch, automated tests pass, a peer has reviewed the code, QA has verified acceptance criteria, and documentation is updated if applicable.


## Ceremonies

Even without sprints, a few lightweight ceremonies keep the team aligned.

**Daily standup (15 min).** Walk the board right to left. Focus on blockers and items closest to Done rather than individual status updates.

**Replenishment meeting (weekly, 30 min).** The Product Owner and team review the Backlog, refine upcoming items, and ensure the Ready column stays healthy.

**Delivery review (bi-weekly, 30 min).** Demo recently completed work to stakeholders. Collect feedback and feed it back into the Backlog.

**Retrospective (bi-weekly, 45 min).** Inspect the process itself. Review flow metrics, discuss what's working, and agree on one or two improvements to try next.


## Flow Metrics

Track these to understand and improve your delivery pace.

**Cycle time** — how long a card takes from In Progress to Done. Target: keep it predictable, not necessarily fast.

**Throughput** — number of items completed per week. Use this for forecasting rather than individual velocity.

**WIP age** — how long each in-progress item has been sitting. Items exceeding the team's average cycle time should be flagged for discussion.


## Escalation Path

If a card has been blocked for more than one business day, the assignee raises it with the tech lead. If it remains blocked for two business days, the tech lead escalates to the engineering manager. The goal is fast resolution, not blame.


## Getting Started Checklist

- [ ] Set up the Kanban board (physical or digital tool)
- [ ] Agree on WIP limits as a team
- [ ] Write acceptance criteria for the first five Backlog items
- [ ] Schedule recurring ceremonies on the team calendar
- [ ] Baseline your cycle time after the first two weeks
