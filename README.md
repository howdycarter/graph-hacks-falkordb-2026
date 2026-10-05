# Graph Hacks 2026 — Entry (WeMakeDevs × FalkorDB)

## Objective
Ship a FalkorDB-backed AI agent in the 4-day Graph Hacks sprint (Oct 15–18, 2026) that wins Track 02 (Agent Memory and Coordination) — with the graph as the load-bearing center of the product, per the anti-decoration clause.

## Source of Truth
- Competition rules: `docs/competition.md` (researched from the official WeMakeDevs page, Oct 4 2026)
- Win plan: `docs/win-plan.md`
- Official site: https://www.wemakedevs.org/hackathons/falkordb

## Done When
- [ ] Working agent deployed live (preferred) or with complete local setup instructions + demo video
- [ ] FalkorDB is the primary graph database and central to what the agent does — removal test passes
- [ ] Main FalkorDB implementation is new work completed Oct 15–18 (prep sketches done before are fine)
- [ ] Registered on the WeMakeDevs event panel (Chris-held — registration not yet confirmed)
- [ ] Submitted via the WeMakeDevs panel before **Oct 18, 2026, 11:59 PM IST (1:29 PM CDT)**
- [ ] Blog post drafted (side prize: AirPods 5 for best blog post)
- [ ] Chris explicitly approves the registration and submission before anything goes out

## Acceptance Criteria
- Agent acts on connected data, remembers across sessions, and can show the path behind each answer
- Every line of code explainable — no blind AI-generated code
- Public/synthetic data only in the graph
- Solo entry (teams up to 4 allowed; default is solo unless Chris says otherwise)

## Constraints
- 4 days. Ruthless scope control — one agent loop, one memory model, one demo story
- FalkorDB runs via Docker (`docker pull falkordb/falkordb:latest`); free tier auto-stops on inactivity — plan demo accordingly
- Coding assistants allowed but must be disclosed in spirit: the work must be genuinely understood
- Nothing registers or submits without Chris's explicit approval

## Non-Goals
- Entering all three tracks — one track, done well, beats three thin entries (can revisit if ahead of schedule)
- Production hardening beyond the demo

## Verifier
Chris runs the live demo, passes the "remove FalkorDB" test mentally, reviews the video, then approves submission.
