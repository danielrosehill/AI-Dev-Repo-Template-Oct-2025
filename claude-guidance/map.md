This document provides guidance for the overall/general structure of this repository.

Unless otherwise specified, all paths are relative to base. Ensure that the CWD is properly set.

# Separation Of Concerns

Regardless of the type of project that you are working on, it is essential that the repository design reflects a clear separation between the codebase and other elements.

## Index, Folder Map

You will often find two files at the base of subfolders, index.md and folder-map.md. The first is the index level and may be the only file; it consolidates information. Slash commands may be used to periodically truncate a subfolder by aggregating file content.

map.md provides a navigation / statement of purpose.

## Human Paths

You are working with a human! While the path structure is relatively well defined, expect some degree of variance if documents are being created by hand. The repo map, for example, may be map.md. Use inference to deduce the intended purpose of files and folders so long as that accords with this pattern.

# Repository Structure Overview

## Codebase (`codebase/`)

The codebase base is `codebase/`. No code *for the project* should ever be created at project base or below this level.

- **tests/**: All testing infrastructure including unit, integration, e2e tests, fixtures, and mocks

## Context (`context/`)

In the course of working on this project, the user will wish to provide you with context data (API docs, code snippets, debugging info, etc.).

- **api-docs/**: API documentation and reference materials
- **code-snippets/**: Reusable code snippets and examples
- **debugging/**: Debugging notes and troubleshooting information
- **other-retrieval/**: General reference materials
- **processed/**: Processed context data (ephemeral)
- **special/**: Special-case context (audio, images)
- **user-thoughts/**: User notes and ideas
- **integrations/**: External integration context (third-party, webhooks, auth)
- **data/**: Data schemas, migrations, and seed data

## Documentation (`docs/`)

Documentation storage with clear separation of audience and purpose.

- **external/**: Public-facing documentation
- **for-user/**: Internal documentation for user/team reference
- **from-user/**: Documents provided by the user
- **for-ai/**: Documents for AI reference (fixed processes, guidelines)
- **security/**: Security documentation (threat models, audits, compliance)
- **onboarding/**: Onboarding materials (setup guides, architecture, contribution guide)

## Project Management (`project-mgmt/`)

Project execution tracking, specifications, and delivery management.

- **blockers/**: Current blockers and impediments
- **decisions/**: Project-level decisions and rationale
- **progress-logs/**: Progress updates, handovers, and logbook entries
- **spec/**: Project specifications and requirements
- **tasks/**: Task tracking (by status, kickoff materials)
- **dependencies/**: Dependency management (security audits, upgrades, compatibility)
- **performance/**: Performance tracking (benchmarks, profiling, optimizations)
- **deployment/**: Deployment configs, environments, and rollback plans
- **qa/**: Quality assurance (test plans, results, bug reports)
- **ai-sessions/**: AI interaction tracking (conversation logs, decisions, learnings)

## Planning (`planning/`)

Technical architecture and design decisions (distinct from execution in project-mgmt).

- **decisions/**: Technical and architectural decisions (UI, CSS, strategy, misc)
- **retrospectives/**: Project retrospectives and lessons learned
- **stack/**: Technology stack decisions (frontend, backend, deployment, APIs, MCP)

## First Entry (`first-entry/`)

Temporary staging area for unsorted content that needs categorization.

- **for-ai/**: Files from user for AI to process
- **from-ai/**: AI-generated output awaiting final placement

## Archive (`archive/`)

Treat `archive/` (relative to base) as a place to archive old code, docs, and notes that are no longer needed. You *may* wish to archive old code or delete it. But this decision should be taken in conjunction with the user.

- **code/**: Archived code files
- **docs/**: Outdated documentation
- **notes/**: Old planning materials

## Management (`mgmt/`)

Repository-level administrative files, maintenance scripts, and infrastructure utilities (distinct from project-mgmt which focuses on project execution).

## Repository Reference (`repo-ref/`)

Meta-level documentation about the repository template itself, including guidelines, structure documentation, and usage examples.