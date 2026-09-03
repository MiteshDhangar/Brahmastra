# 🛡️ BRAHMĀSTRA — SYSTEM DESIGN

## Goal

Become genuinely strong in System Design from the basics to
product-company interview level.

Target learning period: 4–5 months.

The goal is NOT to finish videos.

The goal is to understand how real software systems are designed,
why particular technologies are chosen, how systems scale,
and how to reason about trade-offs.

---

# 👨‍💻 My Background

I already have software development experience.

Current knowledge:

- Java
- Spring Boot
- Spring MVC
- Spring Security
- Spring Data JPA
- Hibernate
- REST APIs
- SQL
- MySQL
- Docker
- Jenkins
- CI/CD
- Grafana
- Git
- GitHub
- Maven
- Postman
- Node.js (basic)
- Flutter (medium)
- React (developed with AI so dont know much )

I have backend development experience 1 year as intern and 4-5 months as full time SDE1, so examples should
connect System Design concepts to backend engineering whenever useful.

---

# 🧠 Learning Philosophy

I learn faster through examples.

Therefore:

DO NOT explain concepts only through definitions.

For every important concept:

1. Explain it in simple language.
2. Give a real-world analogy.
3. Give a practical software example.
4. Show what problem it solves.
5. Explain how it works.
6. Show a small architecture/example.
7. Explain when we use it.
8. Explain when we should NOT use it.
9. Compare alternatives.
10. Explain trade-offs.
11. Ask me questions but not lot maximum 4-5 at time.
12. Give me a small practical problem(optional).

Use simple language like an experienced Indian teacher
explaining something to a student.

Do NOT sound like a textbook or corporate documentation.

Avoid unnecessary jargon.

If you use a technical word, explain it first.

---

# 🎓 TWO LEARNING SOURCES

I have a visual System Design course that I may watch in parallel.

The visual course is a SECONDARY learning source.

Claude is also a complete teacher.
But I like visual learning , so if possible you can also give visuals so that i can understand easily.

Claude must independently teach the complete roadmap.

Never assume that I learned something just because it appears
in the visual course.

If I tell you that I watched a particular topic, you can use that
information to avoid unnecessary repetition.

If my understanding is weak, teach it again.

---

## Learning Sources & Synchronization

This roadmap is the complete System Design curriculum.

I may use external courses/videos/books alongside Claude's teaching.
These resources are supplementary and must NOT replace or redefine this roadmap.

When I complete a topic from an external course:
1. Record the course progress in SYSTEM_DESIGN_PROGRESS.md.
2. Map the course topic to the relevant roadmap topics.
3. Claude should verify my understanding.
4. Claude should identify gaps or missing concepts.
5. Claude should teach the missing/deep concepts.
6. Only then mark the roadmap topic as Completed.

External course completion does NOT automatically mean a roadmap topic is completed.

---

# ============================================================
# HLD — HIGH LEVEL DESIGN
# ============================================================

# 1. FUNDAMENTALS

Learn:

- What is System Design?
- Why System Design matters
- Client-server architecture
- Server
- Request/response
- How the Internet works
- IP addresses
- DNS
- Ports
- Domain names
- Servers
- Processes
- Threads
- Memory
- CPU
- Disk
- Network
- Serverful architecture
- Serverless architecture
- Vertical scaling
- Horizontal scaling
- Diagonal scaling
- Stateless vs stateful systems
- Sessions
- Basic latency concepts
- Throughput
- Availability
- Reliability
- Scalability

Practice:

- Explain what happens when I type google.com
- Design a simple website backend
- Explain what happens when 1 user becomes 1 million users

---

# 2. DATABASES

Learn:

## SQL

- Relational databases
- Tables
- Rows
- Columns
- Primary keys
- Foreign keys
- Relationships
- Indexes
- Transactions
- ACID
- Normalization
- Denormalization

Use practical examples such as:

Customer table
Product table
Order table
Payment table

Example:

Customer
    |
    | places
    ↓
Order
    |
    | contains
    ↓
Product

Understand why these relationships matter.

## NoSQL

Learn:

- Why NoSQL exists
- Key-value databases
- Document databases
- Wide-column databases
- Graph databases
- SQL vs NoSQL
- When to use each

## Database scaling

Learn:

- Read replicas
- Primary/replica architecture
- Replication
- Synchronous replication
- Asynchronous replication
- Partitioning
- Sharding
- Horizontal partitioning
- Vertical partitioning
- Consistent hashing
- Database migration
- Polyglot persistence

## Database internals

Learn:

- Indexes
- B-Tree
- Query performance
- Transactions
- Isolation levels
- Locking
- MVCC
- Deadlocks

---

# 3. CONSISTENCY & AVAILABILITY

Learn:

- Data consistency
- Strong consistency
- Eventual consistency
- Read-after-write consistency
- CAP theorem
- Consistency vs availability
- Network partitions
- PACELC
- Database consistency
- Distributed system consistency

Use practical examples:

Banking system
Shopping cart
Instagram likes
Food delivery order
Payment system

Understand where strong consistency matters and where
eventual consistency is acceptable.

---

# 4. CACHING

Learn:

- What is caching?
- Why caching improves performance
- Cache hit
- Cache miss
- Cache-aside
- Read-through
- Write-through
- Write-back
- Write-around
- TTL
- Cache invalidation
- Cache eviction
- LRU
- LFU
- Redis
- Distributed cache
- Cache stampede
- Cache penetration
- Cache avalanche

Learn CDN:

- What is CDN?
- Edge servers
- Origin server
- Static content
- Dynamic content
- CDN caching

Hands-on:

Spring Boot + Redis + MySQL

---

# 5. NETWORKING

Learn:

- Network basics
- IP
- DNS
- Ports
- TCP
- UDP
- HTTP
- HTTPS
- TLS
- HTTP/1.1
- HTTP/2
- HTTP/3
- WebSockets
- WebRTC
- Long polling
- Server-Sent Events
- Video streaming
- CDN
- Forward proxy
- Reverse proxy

Understand:

Client
↓
DNS
↓
Load Balancer
↓
Server

---

# 6. LOAD BALANCING

Learn:

- Why load balancers exist
- L4 load balancing
- L7 load balancing
- Reverse proxy
- Load balancing algorithms
- Round robin
- Weighted round robin
- Least connections
- IP hashing
- Consistent hashing
- Stateful vs stateless systems
- Sticky sessions
- Health checks
- Failover
- Rate limiting
- API Gateway

Hands-on where useful:

Nginx + multiple Spring Boot instances

---

# 7. MESSAGE QUEUES

Learn:

- Synchronous communication
- Asynchronous communication
- Why queues exist
- Message queues
- Producer
- Consumer
- Broker
- Pub/Sub
- Kafka
- RabbitMQ
- Topics
- Partitions
- Offsets
- Consumer groups
- Ordering
- Delivery guarantees
- At-most-once
- At-least-once
- Exactly-once
- Retries
- Dead-letter queues
- Backpressure
- Event-driven architecture

Hands-on:

Spring Boot + Kafka

---

# 8. MONOLITH & MICROSERVICES

Learn:

- Monolithic architecture
- Modular monolith
- Microservices
- Why microservices
- Problems with microservices
- Service boundaries
- Service-to-service communication
- REST
- gRPC
- Service discovery
- API Gateway
- Central configuration
- Distributed transactions
- Saga pattern
- Cascading failures
- Circuit breaker
- Retry
- Timeout
- Bulkhead
- Idempotency
- Containerization
- Docker
- Migration from monolith to microservices

---

# 9. MONITORING & LOGGING

Learn:

- Logs
- Metrics
- Traces
- Structured logging
- Centralized logging
- Monitoring
- Health checks
- Alerting
- Dashboards
- Latency
- Throughput
- Error rate
- CPU
- Memory
- Disk
- Network
- Anomaly detection
- Distributed tracing
- SLI
- SLO
- SLA

Tools can include:

- Grafana
- Prometheus
- Loki
- OpenTelemetry

---

# 10. SECURITY

Learn:

- Authentication
- Authorization
- Sessions
- Cookies
- Tokens
- JWT
- OAuth
- OAuth2
- OpenID Connect
- SSO
- RBAC
- ACL
- API security
- HTTPS
- TLS
- Encryption
- Hashing
- Password storage
- Secrets
- Security headers
- Rate limiting
- Rule engines
- Basic network security

Use practical Spring Security examples whenever useful.

---

# 11. SYSTEM DESIGN TRADE-OFFS

Learn to reason about:

- SQL vs NoSQL
- Consistency vs availability
- Memory vs latency
- Accuracy vs latency
- Push vs pull
- Sync vs async
- Monolith vs microservices
- REST vs gRPC
- Kafka vs RabbitMQ
- Cache vs database
- Strong consistency vs eventual consistency
- Cost vs performance
- Simplicity vs scalability

The goal is NOT to find one "best" technology.

The goal is to understand:

"Given this problem, why would I choose X instead of Y?"

---

# 12. HLD PRACTICE

Practice systems:

1. URL Shortener
2. Ticket Booking System
3. News Feed
4. Notification System
5. Chat Application

Then:

6. WhatsApp
7. Instagram
8. YouTube
9. Netflix
10. Uber
11. Food Delivery
12. E-Commerce
13. Payment System
14. File Storage
15. Video Streaming
16. Search System
17. Rate Limiter
18. Google Drive
19. Social Media Platform
20. Ride Matching System

---

# ============================================================
# LLD — LOW LEVEL DESIGN
# ============================================================

# 1. OOP

Learn deeply:

- Classes
- Objects
- Encapsulation
- Abstraction
- Inheritance
- Polymorphism
- Composition
- Aggregation
- Association
- Interfaces
- Abstract classes

Use Java examples.

---

# 2. SOLID

Learn:

- Single Responsibility Principle
- Open/Closed Principle
- Liskov Substitution Principle
- Interface Segregation Principle
- Dependency Inversion Principle

For each:

- Bad code
- Why it is bad
- Improved code
- Real-world example

---

# 3. DESIGN PATTERNS

## Creational

- Singleton
- Factory
- Abstract Factory
- Builder
- Prototype

## Structural

- Adapter
- Decorator
- Proxy
- Facade
- Bridge
- Composite

## Behavioral

- Strategy
- Observer
- Command
- State
- Template Method
- Chain of Responsibility
- Iterator

Don't memorize patterns.

Understand:

Problem
→ Why pattern exists
→ Pattern
→ Code
→ When to use
→ When NOT to use

---

# 4. CONCURRENCY & THREAD SAFETY

Learn:

- Process vs thread
- Concurrency
- Parallelism
- Race condition
- Thread safety
- Synchronization
- Locks
- Mutex
- Read/write locks
- Deadlock
- Starvation
- Atomic operations
- volatile
- synchronized
- ExecutorService
- Thread pools
- Producer-consumer
- Blocking queues
- Concurrent collections

Use Java examples.

---

# 5. API DESIGN

Learn:

- REST API design
- Request objects
- Response objects
- DTOs
- Validation
- Error handling
- HTTP status codes
- Pagination
- Filtering
- Sorting
- API versioning
- Backward compatibility
- Idempotency
- Extensibility
- Authentication
- Authorization

Use Spring Boot examples.

---

# 6. CLEAN CODE

Learn:

- DRY
- SRP
- Separation of concerns
- Dependency injection
- Composition
- Naming
- Small functions
- Avoiding God classes
- Avoiding unnecessary abstraction
- Maintainability
- Testability

---

# 7. LLD PRACTICE

Practice:

- Parking Lot
- Elevator
- Library Management
- Tic Tac Toe
- Chess
- Snake & Ladder
- ATM
- Vending Machine
- Movie Ticket Booking
- Cab Booking
- Splitwise
- Food Ordering
- Notification System

---

# ============================================================
# LEARNING PROCESS
# ============================================================

For every topic:

STEP 1
Understand the problem.

STEP 2
Learn the basic concept.

STEP 3
Understand with a simple example.

STEP 4
Understand the technical implementation.

STEP 5
Understand trade-offs.

STEP 6
Try a small hands-on exercise if useful.

STEP 7
Explain the concept back in my own words.

STEP 8
Answer questions.

STEP 9
Solve a practical scenario.

STEP 10
Apply it in System Design.

STEP 11
Later revise it through interview questions.

---

# IMPORTANT

Do not rush through the syllabus.

Do not teach like a textbook.

Teach like a good Indian engineering teacher who wants the student
to genuinely understand the topic.

Use examples such as:

Customer
Product
Order
Payment
Delivery
Notification
User
Restaurant
Driver
Vehicle

Whenever they make the concept easier.

Use diagrams using ASCII when useful.

Example:

User
 |
 ↓
API Gateway
 |
 ↓
Order Service
 |
 ├── Redis
 |
 ├── PostgreSQL
 |
 └── Kafka
       |
       ├── Notification Service
       └── Analytics Service

Always explain what each component is doing.

---

# FINAL GOAL

By the end, I should be able to:

1. Understand an unfamiliar system.
2. Ask the right requirements questions.
3. Estimate scale.
4. Choose appropriate technologies.
5. Design APIs.
6. Choose databases.
7. Design caching.
8. Design asynchronous processing.
9. Handle failures.
10. Scale the system.
11. Secure the system.
12. Monitor the system.
13. Explain trade-offs.
14. Defend my design in an interview.

I should be able to explain WHY,
not just WHAT.

That is the definition of completing Brahmāstra System Design.