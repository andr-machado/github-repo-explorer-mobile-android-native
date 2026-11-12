# README — GitHub Repo Explorer

> **Scope note:** This is the initial README created in **Phase 1.1 — Create the Android project**, before the build toolchain, dependencies, CI, or any architecture exists. It is intentionally short: it establishes the project's identity and intent so the repository is never empty or unexplained. Architecture, tooling, and feature details are added in later M1 phases (§1.2–8.4 of the M1 plan) and future milestones.

---

## GitHub Repo Explorer

A focused Android app for searching public GitHub repositories, inspecting their recent commit history, and bookmarking projects for offline access.

---

## What the Project Is

- A **single-user, unauthenticated, client-only** Android application.
- Core journey:
  **Search → Results → Repository Detail → Commit History → Bookmark → Bookmarks**
- Bookmarks are stored locally and remain available offline; repository and commit data require network connectivity.

---

## Why It Exists

- Solves a small, real developer workflow problem: quick repository discovery plus local bookmarking.
- Doubles as a portfolio project demonstrating **Android architecture, resilience, and automated testing** — the portfolio value is a stated first-class goal, not a side effect.

---

## Scope — In / Out

**In scope:**

- Repository search
- Repository detail + commit history
- Local bookmarks
- Consistent handling of loading, empty, error, offline, and rate-limited states

**Out of scope:**

- GitHub authentication
- Starring repositories
- Social features
- Custom backend / cloud sync
- Play Store release
- Multi-module architecture

Full rationale lives in the PRD's **Non-Goals** section.

---

## Project Status

- **Current stage:** M1 — Foundations, Phase 1.1 (project initialization).
- **What this means:** The repository has just been created and the Android project initialized. Build toolchain, dependencies, package structure, DI, navigation, tests, CI, and documentation are being added incrementally per the M1 plan.
- **No features are implemented yet.** Search, commit history, and bookmarks arrive in M2–M4.

---

## Tech Stack (Planned)

The project will be built with:

- Kotlin, Jetpack Compose (Material 3)
- MVVM + selective Clean Architecture
- Hilt, Retrofit/OkHttp, Room, Coroutines/Flow
- JUnit, MockK, GitHub Actions CI

> These are **planned** dependencies — not yet present in this phase.

---

## Repository Layout

- At this phase: the standard Android project skeleton (single `app` module, Gradle Wrapper, `.gitignore`).
- The `di/`, `presentation/`, `domain/`, and `data/` package structure is introduced in **Phase 2** and documented then.
- Target package root (preview): source code will live under `com.andrl4b.githubexplorer`, with the layered structure (`data/`, `domain/`, `presentation/`, `di/`) nested beneath it — reinforcing the separation of concerns from the start.

---

## Documentation

- Product Requirements Document — problem, goals, non-goals, flows, milestones.
- Technical Design Document — architecture, error model, data contracts.
- M1 — Foundations Step-by-Step Plan — detailed implementation sequence for this milestone.

---

## Building & Running

> **Placeholder** — build/run instructions are finalized in **Phase 1.2** once the build toolchain is configured.


- **No GitHub account or API key required.**
- Why no API key is needed: the app uses GitHub's unauthenticated public REST API endpoints only, with rate-limit handling built into the design (rate limits are represented as a first-class UI state, not a generic error). This means anyone can clone the repository and run it immediately — no OAuth setup, token management, or credentials to configure.

---

## Roadmap

- **M1 — Foundations:** project skeleton, toolchain, DI, navigation shells, test + CI infrastructure.
- **M2 — Search (MVP).**
- **M3 — Repository Detail & Commit History.**
- **M4 — Bookmarks.**
- **M5 — Resilience, Quality & Documentation.**

---

*This README evolves alongside the project. Expect it to grow substantially through the remaining M1 phases and each subsequent milestone.*