# SDLC Project — Session Context

## Goal
Single interactive HTML page documenting a Kanban-based Agile SDLC. "One guide to rule the process" — complete enough to run, simple as possible.

## Files
- **sdlc-walkthrough.html** — Primary deliverable. Four tabs: Flow (diagram), Stages, Roles, Meetings.
- **kanban-sdlc.md** — Early draft (superseded)
- **sdlc-stage-reference.md** — Early draft (superseded)
- **context.md** — This file

## Stages (10)
1. **Intake** — Capture, triage, prioritise
2. **Refinement** — BA writes user stories + acceptance criteria (locked here). Tech Lead assesses feasibility. Architect brought in for new integrations only. DDL/DML flagged for awareness only.
3. **Design (if needed)** — Mandatory for: M/L items, multi-system, new patterns, or any new integration. S items with no integrations skip to Dev. Architect has final say on integration decisions. System Integration Register updated here.
4. **Development** — Developer prompts/steers Claude Code. Tech Lead tracks work items. PM tracks user stories.
5. **Code Review** — Peer reviews AI output. Includes security review. Reject → back to Dev. CI auto-validates unit tests.
6. **DEV Verification** — Developer smoke tests in DEV. Requests QA promotion via Jira status.
7. **Testing & QA** — QA is gatekeeper for QA/Test env. Approves promotion from DEV. Maintains + updates regression suite each release.
8. **UAT** — BA + stakeholders verify business rules.
9. **Deployment** — DevOps deploys. Demo scheduled post-deployment. Rollback → Production Support.
10. **Production Support** — Monitor, respond, learn. Hotfixes skip stages 1–3, go straight to Dev.

## Failure Paths
- **Code Review reject** → back to Development (Stage 4)
- **QA fail** → back to Development, full cycle (4→5→6→7)
- **UAT fail** → back to Development, full cycle (4→5→6→7→8)
- **Rollback** → triggers Production Support
- **Hotfix** → Production Support → Development (skips Intake, Refinement, Design)

## Environment Pipeline
DEV → QA/Test → UAT → Production
- Merge to main auto-deploys to DEV (CI/CD)
- QA controls promotion from DEV to QA/Test (via Jira status)
- QA pass promotes to UAT
- UAT sign-off + PM approval promotes to Production

## Roles (10)
PM, BA, Developer, Tech Lead, Architect (integration-triggered, final say, owns System Integration Register), Product Designer (stages 2–3 then hands off), QA/Tester (gatekeeper for QA/Test env, maintains regression suite), DevOps, Stakeholders, Claude Code (always human-reviewed)

## Meetings (6)
- **Standup** — Daily, 15 min
- **Backlog Grooming & Refinement** — Weekly, 45 min. Serves both Intake triage and Refinement. One session.
- **Design Review** — Per feature, ~20 min. Architect attends if integrations involved.
- **Release Readiness** — Pre-release. Single meeting covering QA results, UAT status, go/no-go.
- **Demo / Showcase** — Post-deployment.
- **Retrospective** — Bi-weekly, 45 min

## Key Rules
- Acceptance criteria locked at Refinement. Edge cases found later → new work items.
- Architect has final say on integration decisions.
- QA promotion from DEV to QA/Test via Jira status change.
- "Integration" = new DB, third-party service, new technology. DDL/DML = awareness only.
- Terminology: "backlog item" (Intake) becomes "work item" (Refinement onward). Sizing: S/M/L t-shirt sizes.

## Tooling
- Claude Code (primary dev tool), Jira (tracking), Confluence (design docs), OpenAPI/Swagger (API contracts, on Confluence then committed to repo at Dev start), Git (source control), CI/CD (auto-deploy to DEV on merge)

## Audit Findings Resolved
All high and medium findings from the process audit have been addressed: hotfix path added, Design trigger clarified, Release Readiness consolidated to single meeting, Demo connected to flow (post-deployment), failure paths documented with explicit re-entry cycles, security added to Code Review, acceptance criteria locked at Refinement, QA promotion mechanism specified (Jira status), regression suite maintenance assigned, documentation updates added to Deployment outputs.
