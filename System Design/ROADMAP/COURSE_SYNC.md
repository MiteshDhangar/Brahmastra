# 🔄 COURSE SYNC — Udemy Course ↔ Master Curriculum

**External course:** *Mastering System Design: From Basics to Cracking Interviews*
**Instructor:** Rahul Rajat Singh
**Platform:** Udemy — 25 sections · 128 lectures · ~23 hours
**Role:** **Supplementary only.** Not the curriculum.

---

## ⚖️ THE RULE

```
SYSTEM_DESIGN_MASTER.md    →  the syllabus. Fixed. Complete. Source of truth.
Rahul Rajat Singh's course →  a secondary aid. Partial by design.
Claude                     →  the primary teacher. Owns the whole syllabus.
```

- Course covers a topic → **still verify** understanding before marking anything Completed.
- Course does **not** cover a master-curriculum topic → Claude teaches it anyway.
- Course covers something **outside** the curriculum but useful → logged as *Supplementary*, taught briefly, never allowed to displace a core topic.

---

## 🔁 SYNC WORKFLOW

When the student says **"I completed Section N in the course"**:

```
   "I completed Section N"
             |
             v
   1. Look up Section N in the MAPPING TABLE below
             |
             v
   2. Ask 3-5 targeted questions on the mapped units
             |
             v
   3. Compare answers against the "Claude MUST add" column
             |
        +----+-----------------+
        |                      |
     Solid                  Weak / partial
        |                      |
        v                      v
   Course = Completed     Teach the gap properly
   Understanding = Strong        |
   Final = Completed             v
                            Re-test -> then mark
             |
             v
   4. Update SYSTEM_DESIGN_PROGRESS.md (unit rows + session log)
```

**Never:** section watched → topic Completed.

---

## 🗺️ MAPPING TABLE — all 25 sections

### Part A — Fundamentals (Sections 1–10)

| § | Course Section | → Master Units | Course likely covers | ⚠️ Claude MUST add |
|---|---|---|---|---|
| 1 | Introduction (6 lec, 24m) | 1.1 | What/why System Design, evolution over 25 yrs | Nothing major — light section |
| 2 | Networking & Communication (9 lec, 2h26) | 1.2, 5.1, 5.2, 5.8 | IP, DNS, ports, TCP/UDP, proxies | DNS resolution steps in depth, TCP handshake, forward vs reverse proxy distinction, **how** a request reaches one of N servers |
| 3 | Protocols (7 lec, 1h22) | 5.3–5.7 | HTTP, HTTPS, TLS, WebSockets | HTTP/2 vs /3 trade-offs, SSE vs WebSocket **decision**, **WebRTC 🔬**, HLS/DASH streaming |
| 4 | Architectural Patterns (6 lec, 1h23) | 8.1, 8.2, 8.3, 1.4 | Monolith vs microservices, layered, event-driven | Service **boundary reasoning**, **Saga 🔬**, circuit breaker/bulkhead/timeout, gRPC vs REST, Strangler Fig migration |
| 5 | Web Concepts (5 lec, 47m) | 1.2, 5.8, 4.6, L5.1 | REST, APIs, cookies, sessions, CDN basics | **1.6 stateless vs stateful 🚨**, session store options, CDN mechanics, full REST design (L5) |
| 6 | Scalability (5 lec, 59m) | 1.5, 1.6, 2.7, 2.8, 6.1–6.3 | Vertical/horizontal, sharding, load balancing | L4 vs L7 depth, LB **algorithms**, sticky sessions, health checks, **consistent hashing 🔬**, **rate limiting 🔬**, 🛠️ Nginx hands-on |
| 7 | Storage — Database & Storage (7 lec, 1h32) | 2.1–2.10 | SQL vs NoSQL, replication, sharding | **Indexing/B-Tree 🔬**, **ACID + isolation levels/MVCC/deadlocks 🔬**, replication lag reality, **SQL vs NoSQL justification 🚨**, polyglot persistence |
| 8 | Performance (6 lec, 1h34) | 4.1–4.7, 1.7 | Caching, CDN, latency basics | **Redis internals 🔬**, cache stampede/penetration/avalanche, write-through vs write-back, **p50/p95/p99**, 🛠️ Spring Boot + Redis |
| 9 | Reliability, Availability & DR (5 lec, 54m) | 3.1–3.4, 8.6 | Availability, redundancy, failover, DR | **CAP explicitly 🚨**, **PACELC**, strong vs eventual **by name**, read-after-write, idempotency |
| 10 | Security (5 lec, 1h20) | 10.1–10.7 | AuthN/AuthZ, HTTPS, TLS, JWT | **OAuth2/OIDC flows 🔬**, password storage/hashing, secrets management, RBAC modelling, Spring Security tie-in |

### Part B — Case Studies (Sections 11–25)

| § | Course Section | → Master Units | Note |
|---|---|---|---|
| 11 | The System Design Blueprint | 11.1, 12.x prep | ⭐ Important. Cross-check against Claude's requirement-gathering + **estimation** framework 🚨 |
| 12 | URL Shortener (TinyURL) | 12.1 | ✅ direct match |
| 13 | Ticketing System (BookMyShow) | 12.2 | ✅ direct match |
| 14 | News Feed (Twitter/Instagram) | 12.3, 12.7 | ✅ News Feed + much of Instagram |
| 15 | Notification System | 12.4 | ✅ direct match |
| 16 | Chat Application (WhatsApp) | 12.5, 12.6 | ✅ covers both |
| 17 | Auction Platform (eBay) | — | 🆕 **Supplementary.** Not in master. Useful (real-time bidding, concurrency). Optional. |
| 18 | Online Rental (Airbnb) | — | 🆕 **Supplementary.** Not in master. Useful (search + booking + double-booking). Optional. |
| 19 | Cloud Storage (Google Drive/Dropbox) | 12.14, 12.18 | ✅ File Storage + Google Drive |
| 20 | Video Sharing (YouTube) | 12.8, 12.15 | ✅ YouTube + Video Streaming |
| 21 | Search Engine (Google) | 12.16 | ✅ direct match |
| 22 | E-Commerce (Amazon) | 12.12 | ✅ direct match |
| 23 | Taxi Hailing (Uber) | 12.10, 12.20 | ✅ Uber + Ride Matching |
| 24 | Collaborative Doc Editor (Google Docs) | — | 🆕 **Supplementary.** Not in master, but genuinely valuable (CRDT/OT, real-time sync). Recommended. |
| 25 | Final Prep, Mindset & Moving Forward | 11.x | Interview framing. Claude's Interview Mode goes deeper. |

🔬 = deep dive · 🚨 = confirmed personal gap from baseline · 🛠️ = hands-on · ⭐ = high value · 🆕 = supplementary

---

## 🚫 WHAT THIS COURSE DOES **NOT** COVER

Claude owns these **100%**. Finishing all 25 sections will still leave these blank.

### Entire master sections with no course equivalent

| Master Section | Status |
|---|---|
| **7. MESSAGE QUEUES** — Kafka, RabbitMQ, partitions, offsets, consumer groups, delivery guarantees, DLQ, backpressure | ❌ **No dedicated section.** Only brushed as "event-driven" inside §4. **Entirely Claude-owned.** |
| **9. MONITORING & LOGGING** — logs/metrics/traces, distributed tracing, OpenTelemetry, SLI/SLO/SLA, alerting | ❌ **No section at all. Entirely Claude-owned.** |
| **11. TRADE-OFFS** — structured trade-off drills | ❌ Scattered mentions only. Claude-owned. |
| **LLD — all 7 sections** — OOP, SOLID, Design Patterns, Concurrency, API Design, Clean Code, 13 LLD problems | ❌ **Zero coverage. Entirely Claude-owned.** Roughly 40% of the master curriculum. |

### Master case studies missing from the course

| Missing | Master Unit |
|---|---|
| Netflix | 12.9 |
| Food Delivery | 12.11 |
| Payment System | 12.13 |
| Rate Limiter | 12.17 |
| Social Media Platform | 12.19 |

### General blind spots of visual courses

1. **Back-of-envelope estimation** — QPS, storage, bandwidth, server count. 🚨 *confirmed personal gap*
2. **Failure scenarios** — "primary DB dies mid-write, now what?"
3. **Database internals** — B-Tree, MVCC, lock contention, isolation anomalies.
4. **Idempotency & exactly-once semantics** — critical for payments/orders.
5. **Interview delivery** — driving 45 minutes, defending choices under challenge.
6. **Cost** — the trade-off nobody teaches but every real system faces.

---

## 📐 SUGGESTED PAIRING ORDER

Course order and master order are close but not identical. Pair them like this so they reinforce instead of confuse:

| Claude teaches (master order) | Watch alongside |
|---|---|
| HLD 1 — Fundamentals | §1 Introduction, §5 Web Concepts, §6 Scalability |
| HLD 2 — Databases | §7 Storage |
| HLD 3 — Consistency & Availability | §9 Reliability & DR |
| HLD 4 — Caching | §8 Performance |
| HLD 5 — Networking | §2 Networking, §3 Protocols |
| HLD 6 — Load Balancing | §6 Scalability (re-watch) |
| HLD 7 — Message Queues | ❌ *nothing — Claude only* |
| HLD 8 — Microservices | §4 Architectural Patterns |
| HLD 9 — Monitoring | ❌ *nothing — Claude only* |
| HLD 10 — Security | §10 Security |
| HLD 11 — Trade-offs | §11 Blueprint, §25 Final Prep |
| HLD 12 — Practice | §12–§24 case studies |
| LLD 1–7 | ❌ *nothing — Claude only* |

---

## 📋 COURSE PROGRESS LOG

| Date | Section completed | Mapped units | Verification result | Action taken |
|---|---|---|---|---|
| _(none yet)_ | | | | |
