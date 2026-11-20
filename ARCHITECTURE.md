# Portfolio architecture and operating model

## Repository boundaries

This repository is the index and shared operating guide. Each of the 50
projects is intended to become an independent repository after it has a
reviewable implementation and is checked against existing GitHub repositories.
The initial local workspace keeps the first implementation under `projects/`
until it is ready for that boundary.

## Project architecture

Start with a modular monolith or a single-process tool. Separate domain rules
from UI, persistence, and external adapters when those boundaries exist. Add a
database only for durable relational state; document an ERD, constraints,
migrations, seed data, backup, and recovery when one is used.

Each project should record requirements, component boundaries, API/data
contracts, threats, operating instructions, known limits, and test evidence.
Security simulations use isolated environments and synthetic data.

## Change and release workflow

For each milestone, inspect Git status before editing, implement a small
vertical slice, format and statically check it, run relevant tests, update docs,
review the diff, then commit with a descriptive message. Never include secrets.
Before any remote push, review the exact staged files and repository identity.
Never force-push, delete repositories, or publish credentials.

## Current host constraints

The development host is Termux on Android ARM64. Docker Desktop and graphical
IDE assumptions are unsuitable. Use portable command-line tools and remote CI
for heavy builds. In the current Codex session, `LD_LIBRARY_PATH` points at
Codex's private bundled C++ runtime, which conflicts with Termux Node.js;
invoke Node/npm with `env -u LD_LIBRARY_PATH` for local checks.
