# GitLab MCP Server

**A safety-first GitLab MCP server built for AI agents and controlled automation.**

> **Status:** Public beta is in preparation. This repository currently contains documentation only. No executable source code has been published yet.

## Why this project

GitLab exposes a powerful API, but an AI agent should not receive unlimited power by default. Useful automation needs clear project boundaries, predictable responses, safe retries, secret redaction, and explicit gates around actions that can change or delete data.

This project is being built around one rule:

> Make common GitLab work easy for agents, and make dangerous work deliberate, visible, and denied by default.

## Internal implementation today

The private development version is already a substantial working system:

- **87 registered MCP tools** across **18 functional modules**;
- **25 focused test modules**;
- coverage for projects, groups, issues, milestones, merge requests, discussions, notes, pipelines, jobs, commits, branches, repository files, tags, releases, wiki pages, variables, labels, and cross-links;
- higher-level workflows for merge-request readiness, pipeline waiting, blocker checks, and controlled bulk operations.

These numbers describe the internal implementation. They do **not** mean that all tools will be included in the first public release.

## What makes it different

The server is designed for real agent workflows, not only one-off API calls.

### Broad GitLab coverage

It connects the main parts of software delivery into one MCP surface:

- project and group discovery;
- issue planning and dependency links;
- merge-request review and discussion handling;
- pipeline, job, and log inspection;
- repository, branch, commit, tag, and release workflows;
- labels, milestones, variables, wiki pages, and notes.

### Safety-first behavior

The internal implementation includes controls such as:

- **fail-closed policy checks** — missing or invalid safety configuration denies the action;
- **explicit project allowlists** — agents can be limited to named projects;
- **deny-before-network behavior** — blocked actions are rejected before a GitLab request is sent;
- **dry-run support** for state-changing workflows;
- **protected target-branch rules** for merge operations;
- **secret redaction** in responses, errors, diagnostics, and audit records;
- **bounded pagination and response size** to avoid unplanned broad reads;
- **safe retry rules** — uncertain mutations are not silently repeated;
- **sanitized audit records** for controlled operations;
- **explicit confirmation gates** for destructive or high-impact tools.

Safety controls reduce risk, but they do not replace least-privilege GitLab credentials, project permissions, review, or operator judgment.

## First public beta

The first public release will intentionally be smaller than the internal server. It will be a clean, independent, **read-only** profile.

Planned properties:

- explicit GitLab project allowlists;
- common project, issue, merge-request, pipeline, commit, and repository inspection;
- sanitized diagnostics;
- bounded output and pagination;
- pinned dependencies;
- reproducible local stdio setup;
- no private infrastructure details or inherited private Git history.

The first beta will **not** include merge, approval, pipeline-action, repository-write, token, secret, admin, or autonomous write tools.

## Who it is for

The planned public beta is aimed at:

- developers using MCP-compatible coding agents;
- teams running self-managed GitLab;
- operators who want useful GitLab context without giving an agent broad write access;
- projects that need a clear path from read-only inspection to carefully gated automation.

## Publication roadmap

Before source code is published, the public snapshot must pass cleanup, regression and negative tests, secret-leak checks, an independent security review, and a clean-environment canary.

See the [public beta publication plan](docs/PUBLICATION_PLAN.md) for the exact scope and release gates.

## Installation

Not available yet. The repository is a documentation placeholder until the public source snapshot passes its publication gates.

## License

No license has been selected yet. Until a license is added, no permission is granted to copy, modify, or distribute this repository's contents.
