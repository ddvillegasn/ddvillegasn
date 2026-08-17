# Cesar David Villegas Naranjo

**Founder and General Manager at [INTEGRADAV](https://integradav.com)** — Pereira, Colombia

I build the software that small and mid-sized companies in Colombia actually run on: AI agents that
answer on WhatsApp, internal financial systems, and web products that have to keep working after the
project ends. I lead a four-person team, and I still write and review the code.

Final-year Systems and Computing Engineering at Universidad Tecnológica de Pereira.

---

## INTEGRADAV

An automation, AI and software studio serving businesses across Colombia's Coffee Region. We take a
client from the initial requirements session to a system in production — architecture, build,
deployment and the operating documentation their team needs to run it without us in the room.

My role is both sides of it: I own the technical architecture and I run the company — pricing,
contracts, delivery process and the financial model.

**Winner, Public Innovation Challenge 2026** — Mayor's Office of Pereira, Secretariat of Economic
Development and Competitiveness, for **JOIN**, a civic PWA built with the UTP.

---

## Selected work

Most of what I build is client or product work and lives in private repositories. What follows is
what the systems do and how they are put together.

### Dental Agent — multi-tenant SaaS for dental clinics *(private)*

A conversational AI agent that handles patient enquiries and scheduling over WhatsApp, with separate
dashboards for the receptionist, the practitioner and the operator. Built on **LangGraph** for the
agent's control flow, **FastAPI** with JWT auth and HMAC-verified webhooks, **Supabase/PostgreSQL**
with row-level security for tenant isolation, and a **Next.js 15** admin panel. Containerised with
Docker, deployed on Railway and Vercel with GitHub Actions.

Currently in pilot with a dental clinic in Bogotá.

### INTEGRADAV Finance — internal financial operating system *(private)*

The system the company is actually run on: income, expenses, envelope-style budget allocation,
runway, break-even and scenario planning. **React 19 + Vite + Firebase Auth/Firestore**, shipped as
an installable PWA on Vercel.

The part I care about is the calculation engine — pure functions, no framework, no database, covered
by a test suite validated against the spreadsheet model it replaced. Everything that touches money
is written as a single atomic batch, so the ledger and the budget envelopes cannot drift apart.

### Client platforms *(private)*

**Justicia y Valor** — website and organic SEO for a law firm; **Lifull** — Shopify storefront with
3D product presentation and CRO work; plus the corporate site, built in Next.js and deployed on
Netlify with a PR-and-preview review flow.

---

## Public repositories

### [footy-predictor](https://github.com/ddvillegasn/footy-predictor) · [▶ live demo](https://footy-predictor.streamlit.app/)

Predicts international football matches with a **Dixon-Coles** time-decayed Poisson model and Monte
Carlo simulation, then prices betting markets from the resulting score distribution.

The engineering decision I would point to is that nothing is hardcoded: the time-decay factor, the
ridge penalty, home advantage, simulation count, market lines and value thresholds all come from
YAML config, so the model can be re-tuned without touching code. The README also states plainly what
the outputs are *not* — `expected_goals` is the model's λ, not shot-based xG, and the expected-value
figures are only as good as the model that produced them. A predictor that oversells its own
certainty is worse than no predictor.

`Python` · `pandas` · `NumPy` · `SciPy` · `Streamlit`

### [aco-tsp-python](https://github.com/ddvillegasn/aco-tsp-python)

Ant Colony Optimization applied to the Travelling Salesman Problem, with an interactive lab for
tuning α, β, ρ and Q while watching the pheromone network and convergence curve respond in real
time. Modular package with dataclasses and type hints, and a test suite that checks the properties
that actually matter for a metaheuristic: every solution is a valid Hamiltonian cycle, the pheromone
matrix stays symmetric, the best-so-far curve is monotonically non-increasing, and a reference
instance resolves to its known length.

`Python` · `Streamlit` · `pytest` — with [Valentina Rosas](https://github.com/valenrosasc)

### [distributed-kv-go](https://github.com/ddvillegasn/distributed-kv-go)

A sharded key-value store deployed across separate machines on a LAN: hash-based partitioning,
automatic redirection to the owning node, and read-only replicas that pull from their leader.
University coursework, built on top of an existing open-source engine — the README says exactly
which parts are ours and which are not.

`Go` · `bbolt` · `TOML`

---

## How I approach engineering

**Make the wrong state impossible to reach, rather than detecting it later.** Two related writes
belong in one transaction. If a repair operation can run twice, it has to be idempotent — I have
seen a non-idempotent fix applied twice and silently double a set of balances.

**Security lives in the rules layer, never in the interface.** Hiding a button is not a permission.
If the database will accept the write, the feature is not protected.

**Configuration over constants.** Prices in another currency, model parameters, business
percentages — anything that changes on a different clock than the code belongs in config, with one
place to update it.

**Write down the decision, not just the result.** Every system I maintain carries a record of what
was decided and why, so the next person — often me, months later — does not undo it by accident.

**State the limits of what you built.** A model with a confidence figure, an AI agent that needs
human supervision, a replica that can serve stale reads: naming the boundary is part of delivering
the thing.

---

## Stack

| | |
|---|---|
| **Languages** | Python, JavaScript/TypeScript, Go, SQL |
| **Backend** | FastAPI, Node.js/Express, Django, Flask, REST APIs, JWT, webhooks |
| **Frontend** | React, Next.js (App Router), Tailwind, Vite |
| **AI & automation** | LangGraph, Claude API, OpenAI API, WhatsApp Cloud API, n8n |
| **Data** | PostgreSQL, Supabase, Firestore, SQLite, pandas, NumPy |
| **Infrastructure** | Docker, GitHub Actions, Vercel, Railway, Netlify, Nginx |
| **Quality** | pytest, Selenium, SonarQube, unit and integration testing |

---

## Background

**Universidad Tecnológica de Pereira** — Systems and Computing Engineering, final year.

**SONAR ISC research group** — software quality and automated testing: Selenium for UI test
automation, SonarQube for static analysis and vulnerability detection, unit and integration testing
under Scrum and DevOps practice.

---

## Contact

| | |
|---|---|
| Company | [integradav.com](https://integradav.com) |
| Email | contacto@integradav.com |
| LinkedIn | [linkedin.com/in/cesarvn36](https://www.linkedin.com/in/cesarvn36) |
| Location | Pereira, Risaralda, Colombia |

Open to technical collaboration, partnerships and interesting problems.
