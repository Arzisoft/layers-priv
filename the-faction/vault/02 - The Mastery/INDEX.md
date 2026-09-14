# The Mastery

*The Mastery is where certification meets production.*

These are supplemental courses — deep, focused builds that prove you can architect real systems, not just pass an exam.

## What You'll Get from The Mastery

Each course in The Mastery is a production-grade deep dive — 7 modules, each with a study guide and a 25-question scenario-based exam. No multiple-choice softballs. Every question puts you inside a real build decision and asks what you'd actually do.

Pass all 7 module exams (80% minimum) and you earn the course credential. That credential isn't decorative — it's a verifiable signal that you understand how production systems are actually built, not just how they're described in docs.

---

## Eight Courses at The Mastery

**SaaS Build** walks you through seven layers of building a production SaaS application: dashboard, payments, multi-tenant data, roles and permissions, deployment pipelines, API throttling, and production monitoring. The full stack of what makes SaaS actually work.

**Database Design** takes you deep on the data layer: schema architecture, relationships, indexing, query optimization, migrations, and the patterns that keep your database from becoming the bottleneck that takes your product down at scale.

**Auth** covers the identity and access layer end to end: authentication flows, session management, OAuth, role-based access control, token security, and the patterns that keep unauthorized users out of places they don't belong.

**Next.js Application Build** is the frontend-to-deployment pipeline: Next.js architecture and routing, server and client components, data fetching and caching, API routes and server actions, SEO and performance, Vercel deployment, and shipping a production app. From project setup to live traffic.

**Supabase Backend Build** is the backend infrastructure course: Supabase architecture, Postgres tables and relationships, row-level security policies, auth and user management, storage, realtime and edge functions, backups and environments, and shipping a production backend. The complete backend stack, directed by AI.

**Stripe Payments Build** is the money layer: account architecture, one-time checkout, subscriptions and the billing portal, webhooks as the source of truth, invoices and tax, failed payment recovery, and a live system you can monitor.

**API Product Build** is the difference between an endpoint and a product: API architecture and endpoint design, auth keys and rate limiting, documentation and developer experience, usage metering and billing, versioning and error design, monitoring and uptime, and a live API that other developers pay to use.

**Cursor Mastery** is the tool layer: Cursor setup and configuration, Composer and Chat, multi-file editing across a codebase, rules and context files, debugging, extensions and custom workflows, and the advanced patterns that hold up on production projects. It is the course that makes every other course in this tier faster to build.

## What These Courses Cover

### SaaS Build

**Dashboard & Data Layer.** The interface your users see first and the data architecture underneath it.

**Payments & Billing Engine.** Subscriptions, webhooks, and the billing logic that turns your product into a business.

**Multi-Tenant Data Architecture.** Isolation, shared infrastructure, and the patterns that keep one customer's data from leaking into another's.

**Users, Teams & Role-Based Access.** Permissions that scale from solo users to enterprise teams without a rewrite.

**SaaS Deployment Pipelines.** CI/CD, staging, production — the pipeline that gets your code live without breaking what's already running.

**API Throttling & Usage Metering.** Rate limits, usage tracking, and the controls that protect your infrastructure and your margins.

**Production Monitoring for SaaS.** The observability layer that tells you when something breaks at 2 AM.

### Database Design

**Data Modeling Fundamentals.** Entities, attributes, and the modeling decisions made in the first hour that every query afterwards has to live with.

**Relationships and Normalization Decisions.** One-to-many, many-to-many, and knowing when normalizing further helps and when it just adds joins.

**Indexes and Query Performance.** What an index actually costs, which queries earn one, and how to read a slow query instead of guessing at it.

**Migrations Without Downtime.** Changing a schema under live traffic, in the order that keeps the old code and the new code both working.

**Seeding, Backups and Restores.** Realistic dev data, backups that run, and the restore you have actually tested rather than assumed.

**Scaling and Read Replicas.** Where a single database stops being enough, and what replicas fix versus what they quietly complicate.

**Ship: Production Database.** A schema, indexes, migrations, and a backup policy running in production against real load.

### Auth

**Auth Architecture and Session Models.** Sessions versus tokens, where identity lives, and the architectural choice that shapes every later decision.

**Email, Password and Magic Links.** The flows most users will actually touch, built with hashing, verification, and expiry handled properly.

**Social and SSO Logins.** OAuth providers and enterprise SSO, including what happens when one person arrives through two different doors.

**Roles, Permissions and Teams.** Access control that scales from a solo user to an enterprise org chart without a rewrite.

**Two-Factor and Account Security.** Second factors, recovery codes, and the hardening that turns a stolen password into a failed login.

**Password Reset and Edge Cases.** The unglamorous flows where auth systems leak: resets, lockouts, email changes, and orphaned accounts.

**Ship: Production Auth.** A complete identity layer in production, with sessions, roles, recovery, and the security review to back it.

### Next.js Application Build

**Next.js Architecture and Routing.** App Router, file-based routing, layouts, and the mental model that makes Next.js click.

**Server and Client Components.** The rendering split that defines modern Next.js — what runs where, and why getting it wrong costs you performance.

**Data Fetching and Caching.** Server-side fetching, client-side state, revalidation, and the caching layer that makes your app fast without making it stale.

**API Routes and Server Actions.** Backend logic inside your frontend framework — mutations, form handling, and the patterns that replace standalone API servers.

**SEO, Metadata and Performance.** The optimization layer that determines whether search engines and users find your app worth loading.

**Vercel Deployment and Environments.** Preview deployments, environment variables, edge functions, and the deployment workflow that makes shipping safe.

**Ship: Production Next.js App.** Everything assembled into a production application you deploy and verify.

### Supabase Backend Build

**Supabase Architecture and Project Setup.** The platform architecture, project configuration, and the mental model for directing AI to build on Supabase.

**Postgres Tables and Relationships.** Schema design, foreign keys, joins, and the relational patterns that keep your data clean as it grows.

**Row-Level Security Policies.** The authorization layer built into the database itself — policies that enforce access rules before your application code even runs.

**Auth and User Management.** Supabase Auth, social login, email verification, and the user management flows your app needs from day one.

**Storage, Realtime and Edge Functions.** File uploads, live subscriptions, and serverless compute — the three capabilities that turn a database into a complete backend.

**Backups and Environments.** Point-in-time recovery, branching, staging environments, and the safety nets that keep a bad migration from destroying production data.

**Ship: Production Backend.** A complete production backend, deployed and verified, built from everything in the course.

### Stripe Payments Build

Payments Architecture and Account Setup. Account types, key discipline, and the object model every later layer builds on.

One-Time Checkout Flows. Checkout sessions, a real product catalog, and confirmation that never trusts the redirect.

Subscriptions and Billing Portal. The subscription lifecycle, price models, trials, proration, and self-service billing.

Webhooks and Payment State. Signature verification, idempotency, and the event handling that makes payment state true.

Invoices, Taxes and Receipts. The invoice lifecycle, Stripe Tax, tax IDs, receipts, and credit notes that keep the books clean.

Failed Payments and Dunning. Smart Retries, dunning sequences, grace periods, and the waterfall that recovers earned revenue.

Ship: Live Payment System. Go-live, Radar, PCI scope, and the monitoring that keeps payments from breaking silently.

### API Product Build

**API Architecture and Endpoint Design.** The shape of the product: resources, verbs, payloads, and the design decisions a developer will live with for years.

**Auth Keys and Rate Limiting.** Issuing and revoking keys, scoping what each one can reach, and the throttles that protect your infrastructure and your margins.

**Documentation and Developer Experience.** Where API products succeed or fail. Reference docs, quickstarts, and the first ten minutes that decide whether a developer stays.

**Usage Metering and Billing.** Counting what customers consume and turning that count into revenue, accurately enough to survive a disputed invoice.

**Versioning and Error Design.** Shipping changes without breaking the integrations you already have, and errors that tell a developer what to fix.

**Monitoring and Uptime.** The observability layer and the uptime commitments that separate an API product from an endpoint that happens to be online.

**Ship: Live API Product.** Keys, docs, a developer portal, usage dashboards, and consumption-based billing, running in production.

### Cursor Mastery

**Cursor Setup and Configuration for AI-Directed Building.** The environment itself: models, indexing, privacy settings, and the configuration that decides whether AI reads your whole codebase or guesses at it.

**Composer and Chat: Directing AI Through the Interface.** The two modes you will live in, when each one is the right tool, and how to write the instruction that gets working code back on the first pass.

**Multi-File Editing and Codebase Navigation.** Changes that span a dozen files at once, and the navigation habits that keep a large repository legible to both you and the model.

**Rules, Context Files, and Project Configuration.** The project memory layer. Rules files, context selection, and the standing instructions that stop you re-explaining your conventions in every session.

**Debugging and Error Resolution With Cursor.** Reading a stack trace with the model, isolating the actual failure, and the difference between fixing an error and fixing the cause of it.

**Extensions, Integrations, and Custom Workflows.** Wiring Cursor into the rest of your stack: extensions, terminal, version control, and the repeatable workflows that carry across projects.

**Advanced Cursor Patterns for Production Projects.** What changes when the codebase is real. Large-repo strategy, review discipline, and the patterns that keep AI-assisted work shippable.

## How It Works

Each module has a study guide and an exam. The study guide covers what you need to know and gives you the AI audit prompts to check your own work. The exam is 25 scenario-based questions at 80% to pass. No memorization. You either understand the judgment call or you don't.

Pass all seven exams in a course and you earn the corresponding Mastery Specialist badge. Those badges count toward your CADE Specialist and CADE Distinguished credentials.

Start with Module 1 of any course and work through in order. Each module builds on the one before it.

*Stop building demos. Start building products.*

— Matt Murphy

_Source: https://the-faction.mn.co/spaces/24191170/content_

## Modules

### 01 — Module 1 — Dashboard & Data Layer
- [Module 01: SaaS Dashboard — Study Guide](01 - Module 1 - Dashboard & Data Layer/01 - Module 01 SaaS Dashboard - Study Guide/lesson.md)
- [Module 01: SaaS Dashboard — Exam](01 - Module 1 - Dashboard & Data Layer/02 - Module 01 SaaS Dashboard - Exam/lesson.md) *(exam)*

### 02 — Module 2 — Payments & Billing Engine
- [Module 02: Subscription Endpoints & Webhooks — Study Guide](02 - Module 2 - Payments & Billing Engine/01 - Module 02 Subscription Endpoints & Webhooks - Study Guide/lesson.md)
- [Module 02: Subscription Endpoints & Webhooks — Exam](02 - Module 2 - Payments & Billing Engine/02 - Module 02 Subscription Endpoints & Webhooks - Exam/lesson.md) *(exam)*

### 03 — Module 3 — Multi-Tenant Architecture
- [Module 03: Multi-Tenant Data Architecture — Study Guide](03 - Module 3 - Multi-Tenant Architecture/01 - Module 03 Multi-Tenant Data Architecture - Study Guide/lesson.md)
- [Module 03: Multi-Tenant Data Architecture — Exam](03 - Module 3 - Multi-Tenant Architecture/02 - Module 03 Multi-Tenant Data Architecture - Exam/lesson.md) *(exam)*

### 04 — Module 4 — Access Control & Permissions
- [Module 04: Users, Teams & RBAC — Study Guide](04 - Module 4 - Access Control & Permissions/01 - Module 04 Users, Teams & RBAC - Study Guide/lesson.md)
- [Module 04: Users, Teams & RBAC — Exam](04 - Module 4 - Access Control & Permissions/02 - Module 04 Users, Teams & RBAC - Exam/lesson.md) *(exam)*

### 05 — Module 5 — Deployment & Infrastructure
- [Module 05: SaaS Deployment Pipelines — Study Guide](05 - Module 5 - Deployment & Infrastructure/01 - Module 05 SaaS Deployment Pipelines - Study Guide/lesson.md)
- [Module 05: SaaS Deployment Pipelines — Exam](05 - Module 5 - Deployment & Infrastructure/02 - Module 05 SaaS Deployment Pipelines - Exam/lesson.md) *(exam)*

### 06 — Module 6 — Usage Metering & Analytics
- [Module 06: API Throttling & Usage Metering — Study Guide](06 - Module 6 - Usage Metering & Analytics/01 - Module 06 API Throttling & Usage Metering - Study Guide/lesson.md)
- [Module 06: API Throttling & Usage Metering — Exam](06 - Module 6 - Usage Metering & Analytics/02 - Module 06 API Throttling & Usage Metering - Exam/lesson.md) *(exam)*

### 07 — Module 7 — Monitoring & Observability
- [Module 07: Production Monitoring for SaaS — Study Guide](07 - Module 7 - Monitoring & Observability/01 - Module 07 Production Monitoring for SaaS - Study Guide/lesson.md)
- [Module 07: Production Monitoring for SaaS — Exam](07 - Module 7 - Monitoring & Observability/02 - Module 07 Production Monitoring for SaaS - Exam/lesson.md) *(exam)*

### 08 — Module 1: Data Modeling Fundamentals
- [Module 1: Data Modeling Fundamentals — Study Guide](08 - Module 1 Data Modeling Fundamentals/01 - Module 1 Data Modeling Fundamentals - Study Guide/lesson.md)
- [Module 1: Data Modeling Fundamentals — Exam](08 - Module 1 Data Modeling Fundamentals/02 - Module 1 Data Modeling Fundamentals - Exam/lesson.md) *(exam)*

### 09 — Module 2: Relationships and Normalization Decisions
- [Module 2: Relationships and Normalization Decisions — Study Guide](09 - Module 2 Relationships and Normalization Decisions/01 - Module 2 Relationships and Normalization Decisions - Study Guide/lesson.md)
- [Module 2: Relationships and Normalization Decisions — Exam](09 - Module 2 Relationships and Normalization Decisions/02 - Module 2 Relationships and Normalization Decisions - Exam/lesson.md) *(exam)*

### 10 — Module 3: Indexes and Query Performance
- [Module 3: Indexes and Query Performance — Study Guide](10 - Module 3 Indexes and Query Performance/01 - Module 3 Indexes and Query Performance - Study Guide/lesson.md)
- [Module 3: Indexes and Query Performance — Exam](10 - Module 3 Indexes and Query Performance/02 - Module 3 Indexes and Query Performance - Exam/lesson.md) *(exam)*

### 11 — Module 4: Migrations Without Downtime
- [Module 4: Migrations Without Downtime — Study Guide](11 - Module 4 Migrations Without Downtime/01 - Module 4 Migrations Without Downtime - Study Guide/lesson.md)
- [Module 4: Migrations Without Downtime — Exam](11 - Module 4 Migrations Without Downtime/02 - Module 4 Migrations Without Downtime - Exam/lesson.md) *(exam)*

### 12 — Module 5: Seeding, Backups and Restores
- [Module 5: Seeding, Backups and Restores — Study Guide](12 - Module 5 Seeding, Backups and Restores/01 - Module 5 Seeding, Backups and Restores - Study Guide/lesson.md)
- [Module 5: Seeding, Backups and Restores — Exam](12 - Module 5 Seeding, Backups and Restores/02 - Module 5 Seeding, Backups and Restores - Exam/lesson.md) *(exam)*

### 13 — Module 6: Scaling and Read Replicas
- [Module 6: Scaling and Read Replicas — Study Guide](13 - Module 6 Scaling and Read Replicas/01 - Module 6 Scaling and Read Replicas - Study Guide/lesson.md)
- [Module 6: Scaling and Read Replicas — Exam](13 - Module 6 Scaling and Read Replicas/02 - Module 6 Scaling and Read Replicas - Exam/lesson.md) *(exam)*

### 14 — Module 7: Ship: Production Database
- [Module 7: Ship: Production Database — Study Guide](14 - Module 7 Ship Production Database/01 - Module 7 Ship Production Database - Study Guide/lesson.md)
- [Module 7: Ship: Production Database — Exam](14 - Module 7 Ship Production Database/02 - Module 7 Ship Production Database - Exam/lesson.md) *(exam)*

### 15 — Module 1: Auth Architecture and Session Models
- [Module 1: Auth Architecture and Session Models — Study Guide](15 - Module 1 Auth Architecture and Session Models/01 - Module 1 Auth Architecture and Session Models - Study Guide/lesson.md)
- [Module 1: Auth Architecture and Session Models — Exam](15 - Module 1 Auth Architecture and Session Models/02 - Module 1 Auth Architecture and Session Models - Exam/lesson.md) *(exam)*

### 16 — Module 2: Email, Password and Magic Links
- [Module 2: Email, Password and Magic Links — Study Guide](16 - Module 2 Email, Password and Magic Links/01 - Module 2 Email, Password and Magic Links - Study Guide/lesson.md)
- [Module 2: Email, Password and Magic Links — Exam](16 - Module 2 Email, Password and Magic Links/02 - Module 2 Email, Password and Magic Links - Exam/lesson.md) *(exam)*

### 17 — Module 3: Social and SSO Logins
- [Module 3: Social and SSO Logins — Study Guide](17 - Module 3 Social and SSO Logins/01 - Module 3 Social and SSO Logins - Study Guide/lesson.md)
- [Module 3: Social and SSO Logins — Exam](17 - Module 3 Social and SSO Logins/02 - Module 3 Social and SSO Logins - Exam/lesson.md) *(exam)*

### 18 — Module 4: Roles, Permissions and Teams
- [Module 4: Roles, Permissions and Teams — Study Guide](18 - Module 4 Roles, Permissions and Teams/01 - Module 4 Roles, Permissions and Teams - Study Guide/lesson.md)
- [Module 4: Roles, Permissions and Teams — Exam](18 - Module 4 Roles, Permissions and Teams/02 - Module 4 Roles, Permissions and Teams - Exam/lesson.md) *(exam)*

### 19 — Module 5: Two-Factor and Account Security
- [Module 5: Two-Factor and Account Security — Study Guide](19 - Module 5 Two-Factor and Account Security/01 - Module 5 Two-Factor and Account Security - Study Guide/lesson.md)
- [Module 5: Two-Factor and Account Security — Exam](19 - Module 5 Two-Factor and Account Security/02 - Module 5 Two-Factor and Account Security - Exam/lesson.md) *(exam)*

### 20 — Module 6: Password Reset and Edge Cases
- [Module 6: Password Reset and Edge Cases — Study Guide](20 - Module 6 Password Reset and Edge Cases/01 - Module 6 Password Reset and Edge Cases - Study Guide/lesson.md)
- [Module 6: Password Reset and Edge Cases — Exam](20 - Module 6 Password Reset and Edge Cases/02 - Module 6 Password Reset and Edge Cases - Exam/lesson.md) *(exam)*

### 21 — Module 7: Ship: Production Auth
- [Module 7: Ship: Production Auth — Study Guide](21 - Module 7 Ship Production Auth/01 - Module 7 Ship Production Auth - Study Guide/lesson.md)
- [Module 7: Ship: Production Auth — Exam](21 - Module 7 Ship Production Auth/02 - Module 7 Ship Production Auth - Exam/lesson.md) *(exam)*

### 22 — Module 1 — Next.js Architecture and Routing
- [Module 1: Next.js Architecture and Routing — Study Guide](22 - Module 1 - Next.js Architecture and Routing/01 - Module 1 Next.js Architecture and Routing - Study Guide/lesson.md)
- [Module 1: Next.js Architecture and Routing — Exam](22 - Module 1 - Next.js Architecture and Routing/02 - Module 1 Next.js Architecture and Routing - Exam/lesson.md) *(exam)*

### 23 — Module 2 — Server and Client Components
- [Module 2: Server and Client Components — Study Guide](23 - Module 2 - Server and Client Components/01 - Module 2 Server and Client Components - Study Guide/lesson.md)
- [Module 2: Server and Client Components — Exam](23 - Module 2 - Server and Client Components/02 - Module 2 Server and Client Components - Exam/lesson.md) *(exam)*

### 24 — Module 3 — Data Fetching and Caching
- [Module 3: Data Fetching and Caching — Study Guide](24 - Module 3 - Data Fetching and Caching/01 - Module 3 Data Fetching and Caching - Study Guide/lesson.md)
- [Module 3: Data Fetching and Caching — Exam](24 - Module 3 - Data Fetching and Caching/02 - Module 3 Data Fetching and Caching - Exam/lesson.md) *(exam)*

### 25 — Module 4 — API Routes and Server Actions
- [Module 4: API Routes and Server Actions — Study Guide](25 - Module 4 - API Routes and Server Actions/01 - Module 4 API Routes and Server Actions - Study Guide/lesson.md)
- [Module 4: API Routes and Server Actions — Exam](25 - Module 4 - API Routes and Server Actions/02 - Module 4 API Routes and Server Actions - Exam/lesson.md) *(exam)*

### 26 — Module 5 — SEO Metadata and Performance
- [Module 5: SEO Metadata and Performance — Study Guide](26 - Module 5 - SEO Metadata and Performance/01 - Module 5 SEO Metadata and Performance - Study Guide/lesson.md)
- [Module 5: SEO Metadata and Performance — Exam](26 - Module 5 - SEO Metadata and Performance/02 - Module 5 SEO Metadata and Performance - Exam/lesson.md) *(exam)*

### 27 — Module 6 — Vercel Deployment and Environments
- [Module 6: Vercel Deployment and Environments — Study Guide](27 - Module 6 - Vercel Deployment and Environments/01 - Module 6 Vercel Deployment and Environments - Study Guide/lesson.md)
- [Module 6: Vercel Deployment and Environments — Exam](27 - Module 6 - Vercel Deployment and Environments/02 - Module 6 Vercel Deployment and Environments - Exam/lesson.md) *(exam)*

### 28 — Module 7 — Ship: Production Next.js App
- [Module 7: Ship: Production Next.js App — Study Guide](28 - Module 7 - Ship Production Next.js App/01 - Module 7 Ship Production Next.js App - Study Guide/lesson.md)
- [Module 7: Ship: Production Next.js App — Exam](28 - Module 7 - Ship Production Next.js App/02 - Module 7 Ship Production Next.js App - Exam/lesson.md) *(exam)*

### 29 — Module 1 — Supabase Architecture and Project Setup
- [Module 1: Supabase Architecture and Project Setup — Study Guide](29 - Module 1 - Supabase Architecture and Project Setup/01 - Module 1 Supabase Architecture and Project Setup - Study Guide/lesson.md)
- [Module 1: Supabase Architecture and Project Setup — Exam](29 - Module 1 - Supabase Architecture and Project Setup/02 - Module 1 Supabase Architecture and Project Setup - Exam/lesson.md) *(exam)*

### 30 — Module 2 — Postgres Tables and Relationships
- [Module 2: Postgres Tables and Relationships — Study Guide](30 - Module 2 - Postgres Tables and Relationships/01 - Module 2 Postgres Tables and Relationships - Study Guide/lesson.md)
- [Module 2: Postgres Tables and Relationships — Exam](30 - Module 2 - Postgres Tables and Relationships/02 - Module 2 Postgres Tables and Relationships - Exam/lesson.md) *(exam)*

### 31 — Module 3 — Row-Level Security Policies
- [Module 3: Row-Level Security Policies — Study Guide](31 - Module 3 - Row-Level Security Policies/01 - Module 3 Row-Level Security Policies - Study Guide/lesson.md)
- [Module 3: Row-Level Security Policies — Exam](31 - Module 3 - Row-Level Security Policies/02 - Module 3 Row-Level Security Policies - Exam/lesson.md) *(exam)*

### 32 — Module 4 — Auth and User Management
- [Module 4: Auth and User Management — Study Guide](32 - Module 4 - Auth and User Management/01 - Module 4 Auth and User Management - Study Guide/lesson.md)
- [Module 4: Auth and User Management — Exam](32 - Module 4 - Auth and User Management/02 - Module 4 Auth and User Management - Exam/lesson.md) *(exam)*

### 33 — Module 5 — Storage Realtime and Edge Functions
- [Module 5: Storage Realtime and Edge Functions — Study Guide](33 - Module 5 - Storage Realtime and Edge Functions/01 - Module 5 Storage Realtime and Edge Functions - Study Guide/lesson.md)
- [Module 5: Storage Realtime and Edge Functions — Exam](33 - Module 5 - Storage Realtime and Edge Functions/02 - Module 5 Storage Realtime and Edge Functions - Exam/lesson.md) *(exam)*

### 34 — Module 6 — Backups and Environments
- [Module 6: Backups and Environments — Study Guide](34 - Module 6 - Backups and Environments/01 - Module 6 Backups and Environments - Study Guide/lesson.md)
- [Module 6: Backups and Environments — Exam](34 - Module 6 - Backups and Environments/02 - Module 6 Backups and Environments - Exam/lesson.md) *(exam)*

### 35 — Module 7 — Ship: Production Backend
- [Module 7: Ship: Production Backend — Study Guide](35 - Module 7 - Ship Production Backend/01 - Module 7 Ship Production Backend - Study Guide/lesson.md)
- [Module 7: Ship: Production Backend — Exam](35 - Module 7 - Ship Production Backend/02 - Module 7 Ship Production Backend - Exam/lesson.md) *(exam)*

### 36 — Module 1: Stripe Payment Architecture and Account Setup
- [Module 1: Payments Architecture and Account Setup — Study Guide](36 - Module 1 Stripe Payment Architecture and Account Setup/01 - Module 1 Payments Architecture and Account Setup - Study Guide/lesson.md)
- [Module 1: Payments Architecture and Account Setup — Exam](36 - Module 1 Stripe Payment Architecture and Account Setup/02 - Module 1 Payments Architecture and Account Setup - Exam/lesson.md) *(exam)*

### 37 — Module 2: One-Time Checkout Flows
- [Module 2: One-Time Checkout Flows — Study Guide](37 - Module 2 One-Time Checkout Flows/01 - Module 2 One-Time Checkout Flows - Study Guide/lesson.md)
- [Module 2: One-Time Checkout Flows — Exam](37 - Module 2 One-Time Checkout Flows/02 - Module 2 One-Time Checkout Flows - Exam/lesson.md) *(exam)*

### 38 — Module 3: Subscriptions and Billing Portal
- [Module 3: Subscriptions and Billing Portal — Study Guide](38 - Module 3 Subscriptions and Billing Portal/01 - Module 3 Subscriptions and Billing Portal - Study Guide/lesson.md)
- [Module 3: Subscriptions and Billing Portal — Exam](38 - Module 3 Subscriptions and Billing Portal/02 - Module 3 Subscriptions and Billing Portal - Exam/lesson.md) *(exam)*

### 39 — Module 4: Webhooks and Payment State
- [Module 4: Webhooks and Payment State — Study Guide](39 - Module 4 Webhooks and Payment State/01 - Module 4 Webhooks and Payment State - Study Guide/lesson.md)
- [Module 4: Webhooks and Payment State — Exam](39 - Module 4 Webhooks and Payment State/02 - Module 4 Webhooks and Payment State - Exam/lesson.md) *(exam)*

### 40 — Module 5: Invoices, Taxes and Receipts
- [Module 5: Invoices, Taxes and Receipts — Study Guide](40 - Module 5 Invoices, Taxes and Receipts/01 - Module 5 Invoices, Taxes and Receipts - Study Guide/lesson.md)
- [Module 5: Invoices, Taxes and Receipts — Exam](40 - Module 5 Invoices, Taxes and Receipts/02 - Module 5 Invoices, Taxes and Receipts - Exam/lesson.md) *(exam)*

### 41 — Module 6: Failed Payments and Dunning
- [Module 6: Failed Payments and Dunning — Study Guide](41 - Module 6 Failed Payments and Dunning/01 - Module 6 Failed Payments and Dunning - Study Guide/lesson.md)
- [Module 6: Failed Payments and Dunning — Exam](41 - Module 6 Failed Payments and Dunning/02 - Module 6 Failed Payments and Dunning - Exam/lesson.md) *(exam)*

### 42 — Module 7: Ship: Live Payment System
- [Module 7: Ship: Live Payment System — Study Guide](42 - Module 7 Ship Live Payment System/01 - Module 7 Ship Live Payment System - Study Guide/lesson.md)
- [Module 7: Ship: Live Payment System — Exam](42 - Module 7 Ship Live Payment System/02 - Module 7 Ship Live Payment System - Exam/lesson.md) *(exam)*

### 43 — Module 1: API Architecture and Endpoint Design
- [Module 1: API Architecture and Endpoint Design — Study Guide](43 - Module 1 API Architecture and Endpoint Design/01 - Module 1 API Architecture and Endpoint Design - Study Guide/lesson.md)
- [Module 1: API Architecture and Endpoint Design — Exam](43 - Module 1 API Architecture and Endpoint Design/02 - Module 1 API Architecture and Endpoint Design - Exam/lesson.md) *(exam)*

### 44 — Module 2: Auth Keys and Rate Limiting
- [Module 2: Auth Keys and Rate Limiting — Study Guide](44 - Module 2 Auth Keys and Rate Limiting/01 - Module 2 Auth Keys and Rate Limiting - Study Guide/lesson.md)
- [Module 2: Auth Keys and Rate Limiting — Exam](44 - Module 2 Auth Keys and Rate Limiting/02 - Module 2 Auth Keys and Rate Limiting - Exam/lesson.md) *(exam)*

### 45 — Module 3: Documentation and Developer Experience
- [Module 3: Documentation and Developer Experience — Study Guide](45 - Module 3 Documentation and Developer Experience/01 - Module 3 Documentation and Developer Experience - Study Guide/lesson.md)
- [Module 3: Documentation and Developer Experience — Exam](45 - Module 3 Documentation and Developer Experience/02 - Module 3 Documentation and Developer Experience - Exam/lesson.md) *(exam)*

### 46 — Module 4: Usage Metering and Billing
- [Module 4: Usage Metering and Billing — Study Guide](46 - Module 4 Usage Metering and Billing/01 - Module 4 Usage Metering and Billing - Study Guide/lesson.md)
- [Module 4: Usage Metering and Billing — Exam](46 - Module 4 Usage Metering and Billing/02 - Module 4 Usage Metering and Billing - Exam/lesson.md) *(exam)*

### 47 — Module 5: Versioning and Error Design
- [Module 5: Versioning and Error Design — Study Guide](47 - Module 5 Versioning and Error Design/01 - Module 5 Versioning and Error Design - Study Guide/lesson.md)
- [Module 5: Versioning and Error Design — Exam](47 - Module 5 Versioning and Error Design/02 - Module 5 Versioning and Error Design - Exam/lesson.md) *(exam)*

### 48 — Module 6: Monitoring and Uptime
- [Module 6: Monitoring and Uptime — Study Guide](48 - Module 6 Monitoring and Uptime/01 - Module 6 Monitoring and Uptime - Study Guide/lesson.md)
- [Module 6: Monitoring and Uptime — Exam](48 - Module 6 Monitoring and Uptime/02 - Module 6 Monitoring and Uptime - Exam/lesson.md) *(exam)*

### 49 — Module 7: Ship: Live API Product
- [Module 7: Ship: Live API Product — Study Guide](49 - Module 7 Ship Live API Product/01 - Module 7 Ship Live API Product - Study Guide/lesson.md)
- [Module 7: Ship: Live API Product — Exam](49 - Module 7 Ship Live API Product/02 - Module 7 Ship Live API Product - Exam/lesson.md) *(exam)*

### 50 — Module 1: Cursor Setup and Configuration for AI-Directed Building
- [Module 1: Cursor Setup and Configuration for AI-Directed Building — Study Guide](50 - Module 1 Cursor Setup and Configuration for AI-Directed Building/01 - Module 1 Cursor Setup and Configuration for AI-Directed Building - Stu/lesson.md)
- [Module 1: Cursor Setup and Configuration for AI-Directed Building — Exam](50 - Module 1 Cursor Setup and Configuration for AI-Directed Building/02 - Module 1 Cursor Setup and Configuration for AI-Directed Building - Exa/lesson.md) *(exam)*

### 51 — Module 2: Composer and Chat: Directing AI Through the Interface
- [Module 2: Composer and Chat: Directing AI Through the Interface — Study Guide](51 - Module 2 Composer and Chat Directing AI Through the Interface/01 - Module 2 Composer and Chat Directing AI Through the Interface - Study/lesson.md)
- [Module 2: Composer and Chat: Directing AI Through the Interface — Exam](51 - Module 2 Composer and Chat Directing AI Through the Interface/02 - Module 2 Composer and Chat Directing AI Through the Interface - Exam/lesson.md) *(exam)*

### 52 — Module 3: Multi-File Editing and Codebase Navigation
- [Module 3: Multi-File Editing and Codebase Navigation — Study Guide](52 - Module 3 Multi-File Editing and Codebase Navigation/01 - Module 3 Multi-File Editing and Codebase Navigation - Study Guide/lesson.md)
- [Module 3: Multi-File Editing and Codebase Navigation — Exam](52 - Module 3 Multi-File Editing and Codebase Navigation/02 - Module 3 Multi-File Editing and Codebase Navigation - Exam/lesson.md) *(exam)*

### 53 — Module 4: Rules, Context Files, and Project Configuration
- [Module 4: Rules, Context Files, and Project Configuration — Study Guide](53 - Module 4 Rules, Context Files, and Project Configuration/01 - Module 4 Rules, Context Files, and Project Configuration - Study Guide/lesson.md)
- [Module 4: Rules, Context Files, and Project Configuration — Exam](53 - Module 4 Rules, Context Files, and Project Configuration/02 - Module 4 Rules, Context Files, and Project Configuration - Exam/lesson.md) *(exam)*

### 54 — Module 5: Debugging and Error Resolution With Cursor
- [Module 5: Debugging and Error Resolution With Cursor — Study Guide](54 - Module 5 Debugging and Error Resolution With Cursor/01 - Module 5 Debugging and Error Resolution With Cursor - Study Guide/lesson.md)
- [Module 5: Debugging and Error Resolution With Cursor — Exam](54 - Module 5 Debugging and Error Resolution With Cursor/02 - Module 5 Debugging and Error Resolution With Cursor - Exam/lesson.md) *(exam)*

### 55 — Module 6: Extensions, Integrations, and Custom Workflows
- [Module 6: Extensions, Integrations, and Custom Workflows — Study Guide](55 - Module 6 Extensions, Integrations, and Custom Workflows/01 - Module 6 Extensions, Integrations, and Custom Workflows - Study Guide/lesson.md)
- [Module 6: Extensions, Integrations, and Custom Workflows — Exam](55 - Module 6 Extensions, Integrations, and Custom Workflows/02 - Module 6 Extensions, Integrations, and Custom Workflows - Exam/lesson.md) *(exam)*

### 56 — Module 7: Advanced Cursor Patterns for Production Projects
- [Module 7: Advanced Cursor Patterns for Production Projects — Study Guide](56 - Module 7 Advanced Cursor Patterns for Production Projects/01 - Module 7 Advanced Cursor Patterns for Production Projects - Study Guid/lesson.md)
- [Module 7: Advanced Cursor Patterns for Production Projects — Exam](56 - Module 7 Advanced Cursor Patterns for Production Projects/02 - Module 7 Advanced Cursor Patterns for Production Projects - Exam/lesson.md) *(exam)*
