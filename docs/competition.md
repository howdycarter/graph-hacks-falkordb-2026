# Graph Hacks: Context for AI Agents — Official Competition Facts

Researched Oct 4, 2026. Source: the official event page https://www.wemakedevs.org/hackathons/falkordb (live and loading normally — the event is real; this morning's "unconfirmed registration" was a page-render issue, not a dead event).

## Organizers
WeMakeDevs (Kunal Kushwaha's developer community — 200K+ members, established hackathon organizer) × FalkorDB (open-source graph database built for AI agents). This is a recurring event — prior editions have verifiable past projects.

## Key dates
- **Oct 15, 2026, 12:01 AM IST → Oct 18, 2026, 11:59 PM IST**
- Submission deadline: **Oct 18, 11:59 PM IST = 6:29 PM UTC = 1:29 PM CDT**
- FalkorDB Discord is open for the whole event (team-finding, graph-model help)

## The brief
"Agents are only as good as the context they work with." Build a working agent, or group of agents, with **FalkorDB as its context layer** — connected data the agent reasons over, memory it keeps between sessions, a clear picture of how things relate. The agent should act on connected data, remember what it learns, and **show how it got to each answer**.

## Tracks (enter one, two, or all three — each has its own prize)
1. **Agents That Act on Connected Data** — the agent uses the graph to decide and act (fraud investigation, security triage, codebase work). Focus: multi-hop reasoning, graph algorithms as agent tools, tool selection via MCP, explainable results. Prize: **iPhone 18 Pro**
2. **Agent Memory and Coordination** — agents remember across sessions and share state. Focus: episodic/semantic/procedural memory, persistent history, shared state and handoffs, per-user memory isolation. Prize: **PS5 with GTA VI**
3. **Company Brain** — an agent that understands how a company works: people, teams, projects, docs, decisions in one graph. Focus: knowledge from docs/tickets/chats, who owns/knows what, decision traceability, sourced answers. Prize: **M6 Mac Mini**

Side prizes: **AirPods 5** for best project blog post; **t-shirt** for every member of the top 50 teams.

**Total prize pool: $20,000** (per the official page; prizes are hardware + swag, not cash). Note: one third-party research doc from Sept 1 cited $10,000 — the official page as of Oct 4 says $20,000; the official page governs.

## Hard rules (from the official page + rules)
- **FalkorDB must be the primary graph database and support a central part of the product.** The anti-decoration clause: a visualization drawn on top of ordinary storage does not qualify — if the product still works with FalkorDB removed, the graph is decoration.
- **Main FalkorDB implementation must be new work completed during the event.** Prep allowed before: ideas, notes, graph model sketches/diagrams. Reuse allowed: libraries, public APIs, templates, third-party tools, public datasets. "The original work completed during the hackathon will be judged."
- **Solo or teams up to 4.** One team per person. Open worldwide, free to enter, no graph experience required.
- **Coding assistants allowed** — but you remain responsible for the code, architecture, security, and correctness, and you must be able to explain what was built and why. Entirely AI-generated work without meaningful contribution may be rejected.
- **Data policy:** public or synthetic data only. No private, login-protected, paywalled, or personal data in the graph.
- Any language, framework, or deployment platform.
- **Registration:** on WeMakeDevs — free account, hit Register on the event page; team and submission managed from the same panel.
- **Submission:** live deployment preferred; otherwise complete local setup instructions + a working demo video.

## Judging lens (inferred from the brief — no published rubric as of Oct 4)
The brief emphasizes: the graph shapes what the agent does (centrality), memory across sessions, multi-agent coordination, explainability ("show the path behind an answer"), and working software. Optimize for: FalkorDB centrality, a demo where the graph visibly does work, and clear before/after (with graph vs. without).

## Sponsor tech
- FalkorDB: `docker pull falkorDB/falkordb:latest`; official clients for Python, Node.js, Java, Rust, Go, PHP, C#; Cypher query language; FalkorDB Browser for inspection
- Ecosystem: GraphRAG-SDK, QueryWeaver, MCP support, Graphiti, Cognee, LangChain, LlamaIndex integrations
- Note: FalkorDB Cloud free tier auto-stops on inactivity — for a live demo, either keep it warm or self-host during judging

## Source links
- Official event page: https://www.wemakedevs.org/hackathons/falkordb
- FalkorDB docs: https://docs.falkordb.com
- FalkorDB: https://www.falkordb.com
