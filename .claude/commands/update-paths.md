This repository is a template for AI-assisted development projects. 

It provides a modular folder based system intended to create a regimented workspace for projects by delineating areas for planning, documentation.

/mgmt is the base folder for scripts that are *not* publicly shared. Everything else is. You can use /mgmt to add scripts for the upkeep of this template.

## Repo Design

The overall structure is as follows:

- CLAUDE.md provides the foundational guidance to Claude 
- CLAUDE.md refers to more specific guidance documents in claude-guidance. For example, CLAUDE.md contains the instruction that if this is a new repo, setup-instructions.md should be followed. This is done to minimise the ingestion of unnecessary context data. 
- A folder map provides guidance for how to use the various folders in the repo correctly. 

## Policies

Always use relative paths relative to repo base as that will be the cwd that Claude inherits on execution.

There is a script to add .gitkeep into empty folders to ensure population of empty directories as will be required in this template.