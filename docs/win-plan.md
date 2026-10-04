# Plan to Win — Graph Hacks 2026

## Concept: Recall — the agent that remembers

**Track 02: Agent Memory and Coordination.** A multi-agent research team (planner, researcher, critic) that shares a single FalkorDB graph as its working memory. Every finding becomes nodes and edges — entities, claims, sources, decisions, open questions. Every new session queries the graph *first*; handoffs between agents happen through graph state, not prompt stuffing. The demo story: run a research task, close it, come back later with a follow-up — the agent recalls what it learned, connects it to the new question, and **shows the graph path behind its answer**.

One paragraph pitch: today's agents are amnesiacs — every session starts cold, every handoff loses context. Recall gives a team of agents one shared memory in FalkorDB: what was found, what was decided, what's still open. Remove the graph and the agents forget everything — which is exactly the point, and exactly what the anti-decoration clause demands.

## Why it wins — mapped to the judging lens

| What judges look for | How Recall scores |
|---|---|
| **FalkorDB centrality (the anti-decoration clause)** | Structural, not cosmetic: the graph IS the memory. No graph → no cross-session recall, no agent handoffs, no decision trails. The "remove FalkorDB" test is the demo's opening move. |
| **Memory across sessions** | The core loop: write findings as graph on session N, query them on session N+1. Multi-hop Cypher queries surface connections a vector store would miss ("what did we conclude about X, and what evidence supported it?"). |
| **Coordination** | Planner/researcher/critic read and write shared graph state — task status, claims with confidence, open questions. Handoffs are graph transactions, visible in FalkorDB Browser. |
| **Explainability** | Every answer ships with its path: the UI renders the subgraph traversal behind each claim. "Show how it got to each answer" is quoted in the brief — this is a direct hit. |
| **Working software** | Live deployment (or flawless local setup + video). Four days forces a tight, demoable scope — a finished small thing beats an unfinished big thing. |

## Tech approach
- **Stack:** Python (FalkorDB's first-class client) + FastAPI backend; lightweight chat UI (Streamlit for speed, or Next.js if polish time allows) with a graph-path visualization panel
- **FalkorDB:** Docker locally (`docker pull falkordb/falkordb:latest`); Cypher for entity/fact writes and multi-hop recall queries; one graph per user/session namespace (multigraph topology)
- **Agents:** tool-using LLM loop (provider TBD); tools are Cypher-backed: `remember(entity, fact, source)`, `recall(query)`, `trace_path(answer_id)`, `handoff(agent, state)`
- **Memory model:** episodic (session transcripts as linked events), semantic (entities + facts), procedural (what worked — the critic's verdicts as edges). Keep it to these three; don't gold-plate.
- **Seed data:** small synthetic research corpus (a fictional company/tech topic) so the demo has something to remember on day one

## Differentiation vs typical entries
Most Graph Hacks entries will be single-agent chatbots with a graph bolted on for "memory" that could've been a JSON file. Recall's differentiators: (1) **multi-agent** — handoffs through shared graph state, which most entries won't attempt; (2) **the removal test as demo theater** — show the agent with the graph (remembers) vs. without (amnesiac) side by side; (3) **visible paths** — the explainability panel turns the graph from infrastructure into the star of the demo.

## Milestones — 4 days (Oct 15–18; deadline 1:29 PM CDT Oct 18)
- **Day 1, Oct 15 — Graph + loop:** FalkorDB in Docker; schema (entities, facts, sessions, decisions, sources); agent loop with `remember`/`recall` Cypher tools working; one end-to-end remembered fact
- **Day 2, Oct 16 — Team + memory:** planner/researcher/critic agents; handoffs via graph state; cross-session recall query (session N+1 uses session N's graph); per-user graph namespaces
- **Day 3, Oct 17 — Demo surface:** chat UI with answer + graph-path panel; synthetic seed corpus loaded; demo video recorded; deployment live (keep FalkorDB warm or self-host)
- **Day 4, Oct 18 (morning) — Submit:** buffer for breakage; blog post draft (AirPods 5 side prize — Chris writes well, this is +EV); submit via WeMakeDevs panel well before 1:29 PM CDT

**Prep allowed before Oct 15** (do it): graph schema sketches, agent role prompts, UI wireframe, synthetic corpus outline. No FalkorDB implementation code until the gun.

## Biggest risks
1. **Cypher + FalkorDB learning curve in 4 days.** Mitigation: FalkorDB starts with one Docker command; do the schema sketch + a Cypher cheat-sheet as prep; keep queries simple (match/merge patterns, 2–3 hop traversals).
2. **Multi-agent scope explosion.** Mitigation: three fixed roles, handoffs are just graph writes with a status field — no fancy orchestration framework. If it's wobbling on day 2, cut to two agents.
3. **"Explain your code" rule.** Mitigation: no code goes in that can't be defended. Prefer hand-written agent loop over a framework's magic; keep a `docs/architecture.md` as it's built.
4. **Free-tier demo flakiness.** Mitigation: self-host FalkorDB on the demo box, or record the video against a warm instance and note it. Never let the live demo depend on a cold cloud instance.
