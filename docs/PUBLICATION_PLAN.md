# Public beta publication plan

## Goal

Publish a focused GitLab MCP server for AI agents with strong safety defaults and a clean public history.

## Current state

This public repository is a documentation placeholder. No executable source code has been published yet.

The internal implementation currently contains:

- 87 registered MCP tools across 18 GitLab areas;
- 25 focused test modules;
- support for issues, merge requests, pipelines, commits, repository files and branches, groups, milestones, releases, wiki pages, variables, notes, and cross-links;
- safety controls for project boundaries, high-impact actions, secret handling, retries, pagination, and audit records.

These numbers describe the internal development version. The first public beta will intentionally expose a smaller surface.

## First public beta

The first release will be read-only and fail closed.

Planned properties:

- explicit GitLab project allowlists;
- read-only tools for common project inspection and review workflows;
- no merge, approval, pipeline-action, repository-write, token, secret, or admin tools;
- sanitized errors and diagnostics;
- bounded pagination and response size;
- retries only where repeating a request is safe;
- pinned dependencies and reproducible local stdio setup;
- a clean public source history with no private infrastructure details.

## Publication gates

Source code will be published only after all gates pass:

1. remove private URLs, credentials, tokens, local paths, and internal deployment details;
2. extract and verify the small read-only public profile;
3. run focused, regression, negative, and secret-leak tests;
4. complete an independent security review of the exact public snapshot;
5. test installation and operation on a clean external environment;
6. select and add a license;
7. publish setup, configuration, security, and contribution documentation.

## Later, not in the first beta

The following areas may be considered only after the read-only beta proves stable:

- opt-in write tools;
- merge and deployment workflows;
- token lifecycle operations;
- remote transport;
- multi-tenant or OAuth operation;
- autonomous agent actions.

Each addition must keep explicit authority, narrow scope, auditability, and fail-closed defaults.

## Status

Documentation only. The server is not yet available for installation or use from this repository.
