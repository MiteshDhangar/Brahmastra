# 📊 BRAHMĀSTRA — SYSTEM DESIGN PROGRESS

> `SYSTEM_DESIGN_MASTER.md` = **what we intend to learn** (curriculum, fixed).
> `SYSTEM_DESIGN_PROGRESS.md` = **what has actually been learned** (this file, living).
> `COURSE_SYNC.md` = **how the external visual course maps into the curriculum**.

**Student:** SDE-1, ~1.5 yrs backend (Java / Spring Boot / SQL / Docker)
**Target window:** 4–5 months of System Design, then DSA
**Started:** 2026-09-03
**Last updated:** 2026-09-03

---

## ▶️ RESUME HERE

> **Read this first in every new session. This is where we left off.**

| | |
|---|---|
| **Baseline assessment** | ✅ **DONE** — do NOT re-run it. Scorecard is below. |
| **Level** | Beginner in System Design (competent backend dev) |
| **Teaching status** | ⏸️ **Not started yet.** Setup session only. |
| **▶️ NEXT UP** | **HLD Unit 1.2 — Client–server & how the internet really works.** Teach from the beginning. |
| **Then** | 1.3 → 1.5 → 1.6 🚨 → 1.7 + estimation drill 🚨 → 1.8 → Section 2 (Databases) |
| **External course** | ✅ *Mastering System Design: From Basics to Cracking Interviews* — Rahul Rajat Singh (Udemy, 25 sections / 128 lectures / 23h). Fully mapped in `COURSE_SYNC.md`. |
| **Watch alongside 1.2** | §1 Introduction, §5 Web Concepts |
| **Course does NOT cover** | ❌ Message Queues (§7), ❌ Monitoring (§9), ❌ Trade-off drills (§11), ❌ **entire LLD track**, ❌ Netflix / Food Delivery / Payment / Rate Limiter / Social Media case studies |

**Plan for Unit 1.2 (teach in these chunks, one at a time, question after each):**
1. What a server actually *is* — a process listening on a port, not a machine. IP = building, port = shop. Client/server is about *who speaks first*, and the role flips (Spring Boot is a server to the browser, a client to MySQL).
2. DNS — how `google.com` becomes an IP address.
3. TCP connection + the full request journey: browser → DNS → TCP → HTTP → Tomcat → DispatcherServlet → Controller → Service → Repository → MySQL → rows → Jackson → JSON → response → render.
4. What's actually *inside* an HTTP request and response (method, path, headers, status code, body).

> ⚠️ Chunk 1 was previewed briefly in the setup session but **nothing was verified** — no answers were given. Teach it fresh.

**Carry-forward notes for the teacher:**
- Core diagnosis: *knows WHAT tools exist, not HOW they work or WHAT they cost.* Push for mechanism + trade-off on every topic.
- He answers honestly ("I don't know") — trust it, don't over-probe.
- Move **fast** through caching (already Medium). Move **slow** through stateless/stateful and estimation (both blank).
- He prefers **short, tight responses**. No long lectures.
- Estimation must be drilled repeatedly, not taught once.

---

## 🔑 LEGEND

| Column | Values | Meaning |
|---|---|---|
| **Course** | `Not Started` · `In Progress` · `Completed` | External visual course only. Watching ≠ knowing. |
| **Claude** | `Not Started` · `Learning` · `Completed` | Teaching sessions done with Claude. |
| **Understanding** | `—` · `Weak` · `Medium` · `Strong` | Verified by questioning, not by self-report. |
| **Final** | `Not Started` · `Learning` · `Needs Revision` · `Needs Deep Dive` · `Completed` | The only status that actually counts. |

**Rule for `Final = Completed`:** the student must be able to (a) explain it simply, (b) explain how it works in production, (c) defend trade-offs under interview follow-ups. All three. No exceptions.

`🔬` = topic flagged in `CLAUDE_TEACHER.md` as needing a **DEEP DIVE**.
`🛠️` = hands-on / build-it session.

---

## 🎯 BASELINE ASSESSMENT

**Status:** ✅ Completed
**Date:** 2026-09-03

| # | Area probed | Result | Verdict |
|---|---|---|---|
| 1 | Client–server fundamentals | ✅ | Roles correct. Could not describe request/response internals or the path from DB → JSON → screen. |
| 2 | Scaling (vertical vs horizontal) | ⚠️ | Listed correct solutions (bigger server, LB, cache). Could not explain limits until prompted; then got cost + SPOF. Missed hardware ceiling + upgrade downtime. Could not explain **how** a request reaches one of N servers (no DNS→LB→algorithm chain). |
| 3 | Indexing intuition | ⚠️ | Said "indexing" correctly. Did not know full table scan vs B-Tree lookup. Did not know the **write cost** of indexes. |
| 4 | Stateless vs stateful, sessions | ❌ | Complete blank on all three parts. Does not know session affinity, distributed session store, or why in-memory state breaks horizontal scaling. |
| 5 | Caching | ✅✅ | **Strongest area.** Described cache-aside accurately unprompted. Diagnosed stale-cache correctly. Described cache avalanche correctly. |
| 6 | SQL vs NoSQL | ⚠️ | Picked correctly by instinct (SQL=orders, NoSQL=menus) but **could not justify either**. Skipped the high-write case. No knowledge of ACID vs BASE trade-off. |
| 7 | Sync vs async / queues | ⚠️ | Knew `@Async`-style background execution. Did **not** reach for a message queue. No durability reasoning (crash = task lost). Fixed coupling by reordering steps, not decoupling — architectural flaw not identified. |
| 8 | Consistency & CAP | ⚠️ | Correctly picked bank=catastrophe, likes=acceptable. **No vocabulary** — could not name strong vs eventual consistency. No CAP awareness. Trade-off answered vaguely ("costs more"). |
| 9 | Back-of-envelope estimation | ❌ | **Absent.** Writes off by ~6x, reads off by ~60x, storage not attempted. Stated he had "never thought like this." |
| 10 | Open-ended design (URL shortener) | ⚠️ | ~25%. Got the core mapping concept. No formal API design, no DB choice, no collision strategy, did not connect read-heavy workload to caching/replicas. |

### Result summary

**Level: BEGINNER in System Design** (competent backend developer, but System Design specifically is beginner).

**Core diagnosis — one line:**
> He knows **WHAT** tools exist. He does not know **HOW** they work internally, or **WHAT** they cost.
> System design interviews test almost exclusively the second thing.

**Strengths**
1. **Caching** — genuinely solid, described cache-aside and avalanche unprompted. Real working knowledge.
2. **Honest self-reporting** — says "I don't know" instead of bluffing. Rare and extremely valuable for fast progress.
3. **Strong implementation base** — Spring Boot, SQL, Docker, Grafana. Concepts can be anchored to things he has actually run.
4. **Decent instincts** — landed on the right choice in Q6 and Q8 without knowing the theory.

**Gaps (ranked by priority)**
1. **Back-of-envelope estimation** — absent. Blocks every design discussion.
2. **Stateless vs stateful** — total blank. Blocks all horizontal scaling reasoning.
3. **Mechanism-level depth** — full table scan vs B-Tree, DNS→LB routing, how a queue guarantees delivery.
4. **Vocabulary** — cannot name strong/eventual consistency, CAP, cache-aside, idempotency. Knows ideas, not terms.
5. **Trade-off articulation** — never says "I chose X over Y because Z, and I'm accepting cost C."
6. **Async / queue thinking** — no concept of durability or decoupling.
7. **SQL vs NoSQL justification** — ACID vs BASE, joins, schema flexibility.

**Recommended entry point:** HLD Section 1 — Fundamentals. Do **not** skip it. Q1–Q4 exposed real gaps in exactly these units. Prioritised order within Section 1: **1.2 → 1.3 → 1.5 → 1.6 → 1.7 (+ estimation drill) → 1.8**, then straight into Section 2 (Databases).

### Baseline-derived starting states

Units where the baseline already gave us a signal. These override the default `Not Started` in the tables below.

| Unit | Topic | Understanding (baseline) | Note |
|---|---|---|---|
| 1.2 | Client–server / internet | Weak | Roles known, mechanics not |
| 1.5 | Scaling | Weak | Knows names, not limits or routing |
| 1.6 | Stateless vs stateful | **Weak (blank)** | 🚨 highest-priority fundamental |
| 1.7 | Latency/throughput + estimation | **Weak (blank)** | 🚨 estimation must be drilled early |
| 2.3 | Indexes & B-Tree | Weak | Knows "add an index", nothing beneath it |
| 2.6 | SQL vs NoSQL | Weak | Correct instinct, zero justification |
| 3.1 | Consistency models | Weak | Correct instinct, no vocabulary |
| 4.1 | Caching fundamentals | **Medium** | ⭐ genuine working knowledge |
| 4.2 | Caching patterns | **Medium** | ⭐ described cache-aside unprompted |
| 4.5 | Cache failure modes | **Medium** | ⭐ described avalanche unprompted |
| 7.1 | Sync vs async | Weak | Knows `@Async`, not queues/durability |

⭐ = teach faster, verify and move on · 🚨 = do not rush

---

# ============================================================
# HLD — HIGH LEVEL DESIGN
# ============================================================

## 1. FUNDAMENTALS

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 1.1 | What is System Design & why it matters | Not Started | Not Started | — | Not Started |
| 1.2 | Client–server, request/response, how the Internet works (IP, DNS, ports, domains) | Not Started | Not Started | — | Not Started |
| 1.3 | Inside a server: process, thread, CPU, memory, disk, network | Not Started | Not Started | — | Not Started |
| 1.4 | Serverful vs serverless | Not Started | Not Started | — | Not Started |
| 1.5 | Scaling: vertical, horizontal, diagonal | Not Started | Not Started | — | Not Started |
| 1.6 | Stateless vs stateful systems, sessions | Not Started | Not Started | — | Not Started |
| 1.7 | Latency, throughput, availability, reliability, scalability | Not Started | Not Started | — | Not Started |
| 1.8 | Practice: "what happens when I type google.com" + 1 user → 1M users | Not Started | Not Started | — | Not Started |

## 2. DATABASES

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 2.1 | Relational basics: tables, keys, relationships, normalization/denormalization | Not Started | Not Started | — | Not Started |
| 2.2 | Transactions & ACID 🔬 | Not Started | Not Started | — | Not Started |
| 2.3 | Indexes, B-Tree, query performance 🔬 | Not Started | Not Started | — | Not Started |
| 2.4 | Isolation levels, locking, MVCC, deadlocks 🔬 | Not Started | Not Started | — | Not Started |
| 2.5 | NoSQL families: key-value, document, wide-column, graph | Not Started | Not Started | — | Not Started |
| 2.6 | SQL vs NoSQL — decision framework | Not Started | Not Started | — | Not Started |
| 2.7 | Replication: primary/replica, sync vs async, read replicas | Not Started | Not Started | — | Not Started |
| 2.8 | Partitioning & sharding (horizontal / vertical) | Not Started | Not Started | — | Not Started |
| 2.9 | Consistent hashing 🔬 | Not Started | Not Started | — | Not Started |
| 2.10 | Database migration & polyglot persistence | Not Started | Not Started | — | Not Started |

## 3. CONSISTENCY & AVAILABILITY

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 3.1 | Consistency models: strong, eventual, read-after-write | Not Started | Not Started | — | Not Started |
| 3.2 | CAP theorem & network partitions | Not Started | Not Started | — | Not Started |
| 3.3 | PACELC | Not Started | Not Started | — | Not Started |
| 3.4 | Applying consistency: banking, cart, likes, orders, payments | Not Started | Not Started | — | Not Started |

## 4. CACHING

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 4.1 | Caching fundamentals: hit, miss, why memory beats disk | Not Started | Not Started | — | Not Started |
| 4.2 | Patterns: cache-aside, read-through, write-through, write-back, write-around | Not Started | Not Started | — | Not Started |
| 4.3 | TTL, invalidation, eviction (LRU / LFU) | Not Started | Not Started | — | Not Started |
| 4.4 | Redis deep dive 🔬 | Not Started | Not Started | — | Not Started |
| 4.5 | Distributed cache failure modes: stampede, penetration, avalanche | Not Started | Not Started | — | Not Started |
| 4.6 | CDN: edge servers, origin, static vs dynamic content | Not Started | Not Started | — | Not Started |
| 4.7 | Hands-on: Spring Boot + Redis + MySQL 🛠️ | Not Started | Not Started | — | Not Started |

## 5. NETWORKING

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 5.1 | IP, DNS, ports — in depth | Not Started | Not Started | — | Not Started |
| 5.2 | TCP vs UDP | Not Started | Not Started | — | Not Started |
| 5.3 | HTTP, HTTPS, TLS handshake | Not Started | Not Started | — | Not Started |
| 5.4 | HTTP/1.1 vs HTTP/2 vs HTTP/3 | Not Started | Not Started | — | Not Started |
| 5.5 | Real-time: short polling, long polling, SSE, WebSockets | Not Started | Not Started | — | Not Started |
| 5.6 | WebRTC 🔬 | Not Started | Not Started | — | Not Started |
| 5.7 | Video streaming (HLS / DASH, adaptive bitrate) | Not Started | Not Started | — | Not Started |
| 5.8 | Forward proxy vs reverse proxy, CDN placement | Not Started | Not Started | — | Not Started |

## 6. LOAD BALANCING

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 6.1 | Why load balancers exist; L4 vs L7 | Not Started | Not Started | — | Not Started |
| 6.2 | Algorithms: round robin, weighted RR, least connections, IP hash, consistent hashing | Not Started | Not Started | — | Not Started |
| 6.3 | Sticky sessions, health checks, failover | Not Started | Not Started | — | Not Started |
| 6.4 | Rate limiting 🔬 | Not Started | Not Started | — | Not Started |
| 6.5 | API Gateway | Not Started | Not Started | — | Not Started |
| 6.6 | Hands-on: Nginx + multiple Spring Boot instances 🛠️ | Not Started | Not Started | — | Not Started |

## 7. MESSAGE QUEUES

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 7.1 | Synchronous vs asynchronous communication; why queues exist | Not Started | Not Started | — | Not Started |
| 7.2 | Queue fundamentals: producer, consumer, broker, pub/sub | Not Started | Not Started | — | Not Started |
| 7.3 | Kafka deep dive: topics, partitions, offsets, consumer groups, ordering 🔬 | Not Started | Not Started | — | Not Started |
| 7.4 | RabbitMQ deep dive: exchanges, routing, acks 🔬 | Not Started | Not Started | — | Not Started |
| 7.5 | Delivery guarantees (at-most / at-least / exactly-once), retries, DLQ, idempotency | Not Started | Not Started | — | Not Started |
| 7.6 | Backpressure & event-driven architecture | Not Started | Not Started | — | Not Started |
| 7.7 | Hands-on: Spring Boot + Kafka 🛠️ | Not Started | Not Started | — | Not Started |

## 8. MONOLITH & MICROSERVICES

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 8.1 | Monolith, modular monolith, microservices — why and when | Not Started | Not Started | — | Not Started |
| 8.2 | Service boundaries & decomposition | Not Started | Not Started | — | Not Started |
| 8.3 | Service-to-service communication: REST vs gRPC, sync vs async | Not Started | Not Started | — | Not Started |
| 8.4 | Service discovery, API gateway, central configuration | Not Started | Not Started | — | Not Started |
| 8.5 | Distributed transactions & Saga pattern 🔬 | Not Started | Not Started | — | Not Started |
| 8.6 | Resilience: cascading failure, circuit breaker, retry, timeout, bulkhead, idempotency | Not Started | Not Started | — | Not Started |
| 8.7 | Containerization & deployment (Docker) | Not Started | Not Started | — | Not Started |
| 8.8 | Monolith → microservices migration (Strangler Fig) | Not Started | Not Started | — | Not Started |

## 9. MONITORING & LOGGING

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 9.1 | Three pillars: logs, metrics, traces | Not Started | Not Started | — | Not Started |
| 9.2 | Structured logging & centralized logging | Not Started | Not Started | — | Not Started |
| 9.3 | Metrics that matter: latency (p50/p95/p99), throughput, error rate, saturation | Not Started | Not Started | — | Not Started |
| 9.4 | Distributed tracing & OpenTelemetry | Not Started | Not Started | — | Not Started |
| 9.5 | Health checks, alerting, dashboards, anomaly detection | Not Started | Not Started | — | Not Started |
| 9.6 | SLI, SLO, SLA | Not Started | Not Started | — | Not Started |
| 9.7 | Hands-on: Prometheus + Grafana + Spring Boot 🛠️ | Not Started | Not Started | — | Not Started |

## 10. SECURITY

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 10.1 | Authentication vs authorization; sessions, cookies, tokens | Not Started | Not Started | — | Not Started |
| 10.2 | JWT: structure, signing, expiry, refresh, pitfalls | Not Started | Not Started | — | Not Started |
| 10.3 | OAuth2 & OpenID Connect, SSO 🔬 | Not Started | Not Started | — | Not Started |
| 10.4 | RBAC, ACL, API security | Not Started | Not Started | — | Not Started |
| 10.5 | HTTPS/TLS, encryption vs hashing, password storage | Not Started | Not Started | — | Not Started |
| 10.6 | Secrets management, security headers, rate limiting, rule engines | Not Started | Not Started | — | Not Started |
| 10.7 | Basic network security | Not Started | Not Started | — | Not Started |

## 11. SYSTEM DESIGN TRADE-OFFS

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| 11.1 | Trade-off reasoning framework ("given this problem, why X over Y?") | Not Started | Not Started | — | Not Started |
| 11.2 | Trade-off drills: SQL vs NoSQL, C vs A, sync vs async, push vs pull, REST vs gRPC, Kafka vs RabbitMQ, cache vs DB, cost vs performance, simplicity vs scalability | Not Started | Not Started | — | Not Started |

## 12. HLD PRACTICE

| # | System | Attempted | Design Quality | Final |
|---|---|---|---|---|
| 1 | URL Shortener | No | — | Not Started |
| 2 | Ticket Booking System | No | — | Not Started |
| 3 | News Feed | No | — | Not Started |
| 4 | Notification System | No | — | Not Started |
| 5 | Chat Application | No | — | Not Started |
| 6 | WhatsApp | No | — | Not Started |
| 7 | Instagram | No | — | Not Started |
| 8 | YouTube | No | — | Not Started |
| 9 | Netflix | No | — | Not Started |
| 10 | Uber | No | — | Not Started |
| 11 | Food Delivery | No | — | Not Started |
| 12 | E-Commerce | No | — | Not Started |
| 13 | Payment System | No | — | Not Started |
| 14 | File Storage | No | — | Not Started |
| 15 | Video Streaming | No | — | Not Started |
| 16 | Search System | No | — | Not Started |
| 17 | Rate Limiter | No | — | Not Started |
| 18 | Google Drive | No | — | Not Started |
| 19 | Social Media Platform | No | — | Not Started |
| 20 | Ride Matching System | No | — | Not Started |

---

# ============================================================
# LLD — LOW LEVEL DESIGN
# ============================================================

## L1. OOP

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| L1.1 | Classes, objects, encapsulation, abstraction | Not Started | Not Started | — | Not Started |
| L1.2 | Inheritance & polymorphism (compile-time vs runtime) | Not Started | Not Started | — | Not Started |
| L1.3 | Composition, aggregation, association — and "composition over inheritance" | Not Started | Not Started | — | Not Started |
| L1.4 | Interfaces vs abstract classes | Not Started | Not Started | — | Not Started |

## L2. SOLID

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| L2.1 | Single Responsibility Principle | Not Started | Not Started | — | Not Started |
| L2.2 | Open/Closed Principle | Not Started | Not Started | — | Not Started |
| L2.3 | Liskov Substitution Principle | Not Started | Not Started | — | Not Started |
| L2.4 | Interface Segregation Principle | Not Started | Not Started | — | Not Started |
| L2.5 | Dependency Inversion Principle | Not Started | Not Started | — | Not Started |

## L3. DESIGN PATTERNS

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| L3.1 | Creational: Singleton, Factory, Abstract Factory, Builder, Prototype | Not Started | Not Started | — | Not Started |
| L3.2 | Structural: Adapter, Decorator, Proxy, Facade, Bridge, Composite | Not Started | Not Started | — | Not Started |
| L3.3 | Behavioral: Strategy, Observer, Command, State, Template Method, Chain of Responsibility, Iterator | Not Started | Not Started | — | Not Started |
| L3.4 | Pattern selection: problem → pattern (and when NOT to use one) | Not Started | Not Started | — | Not Started |

## L4. CONCURRENCY & THREAD SAFETY

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| L4.1 | Process vs thread; concurrency vs parallelism | Not Started | Not Started | — | Not Started |
| L4.2 | Race conditions, thread safety, `synchronized`, `volatile`, atomics | Not Started | Not Started | — | Not Started |
| L4.3 | Locks, mutex, read/write locks, deadlock, starvation | Not Started | Not Started | — | Not Started |
| L4.4 | ExecutorService, thread pools, sizing | Not Started | Not Started | — | Not Started |
| L4.5 | Producer–consumer, blocking queues, concurrent collections | Not Started | Not Started | — | Not Started |

## L5. API DESIGN

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| L5.1 | REST design: resources, verbs, status codes | Not Started | Not Started | — | Not Started |
| L5.2 | DTOs, request/response objects, validation, error handling | Not Started | Not Started | — | Not Started |
| L5.3 | Pagination, filtering, sorting | Not Started | Not Started | — | Not Started |
| L5.4 | Versioning, backward compatibility, extensibility | Not Started | Not Started | — | Not Started |
| L5.5 | Idempotency, auth in APIs | Not Started | Not Started | — | Not Started |

## L6. CLEAN CODE

| Unit | Topic | Course | Claude | Understanding | Final |
|---|---|---|---|---|---|
| L6.1 | DRY, SRP, separation of concerns | Not Started | Not Started | — | Not Started |
| L6.2 | Dependency injection & composition | Not Started | Not Started | — | Not Started |
| L6.3 | Naming, small functions, avoiding God classes | Not Started | Not Started | — | Not Started |
| L6.4 | Avoiding unnecessary abstraction; maintainability & testability | Not Started | Not Started | — | Not Started |

## L7. LLD PRACTICE

| # | Problem | Attempted | Design Quality | Final |
|---|---|---|---|---|
| 1 | Parking Lot | No | — | Not Started |
| 2 | Elevator | No | — | Not Started |
| 3 | Library Management | No | — | Not Started |
| 4 | Tic Tac Toe | No | — | Not Started |
| 5 | Chess | No | — | Not Started |
| 6 | Snake & Ladder | No | — | Not Started |
| 7 | ATM | No | — | Not Started |
| 8 | Vending Machine | No | — | Not Started |
| 9 | Movie Ticket Booking | No | — | Not Started |
| 10 | Cab Booking | No | — | Not Started |
| 11 | Splitwise | No | — | Not Started |
| 12 | Food Ordering | No | — | Not Started |
| 13 | Notification System | No | — | Not Started |

---

## 📝 SESSION LOG

| Date | Session | Units touched | Outcome |
|---|---|---|---|
| 2026-09-03 | **Session 0 — Setup & Baseline** | none taught | Read `SYSTEM_DESIGN_MASTER.md` + `CLAUDE_TEACHER.md`. Created this file (97 trackable units) and `COURSE_SYNC.md`. Ran the 10-question baseline → **Beginner**. Identified external course (Rahul Rajat Singh, Udemy) and mapped all 25 sections. Updated `CLAUDE_TEACHER.md` so future sessions resume instead of re-testing. **No teaching done.** Next session starts at Unit 1.2 from scratch. |

---

## 🔁 REVISION QUEUE

Topics marked `Needs Revision` or `Needs Deep Dive` get pulled back here automatically.

| Topic | Why | Revisit by |
|---|---|---|
| _(empty)_ | | |

---

## 🎤 INTERVIEW MODE HISTORY

| Date | Problem | Score | Weak areas found |
|---|---|---|---|
| _(none yet)_ | | | |
