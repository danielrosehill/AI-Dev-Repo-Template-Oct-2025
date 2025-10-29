# Hierarchical Context Chain

This document visualizes the context flow architecture for AI agent guidance within this repository.

## Overview Flow

```mermaid
flowchart TD
    A[Entry Point: CLAUDE.md] --> B[Repository Context]
    B --> C[claude-guidance/]
    C --> D[Stage-Specific Context]
    D --> E[Folder Maps]
    E --> F[Project Files]

    style A fill:#4CAF50,stroke:#2E7D32,color:#fff
    style C fill:#2196F3,stroke:#1565C0,color:#fff
    style E fill:#FF9800,stroke:#E65100,color:#fff
```

## Detailed Context Hierarchy

```mermaid
flowchart TB
    Start([AI Agent Starts]) --> Root[/Check for CLAUDE.md\]

    Root --> |Found at repo root| RepoLevel[Load Repository-Level Context]
    Root --> |Check parent dirs| ParentLevel[Load Parent CLAUDE.md]

    RepoLevel --> Purpose[Understand Project Purpose]
    Purpose --> Layout[Review Repository Layout]

    Layout --> CheckStage{Project Stage?}

    CheckStage --> |New Project| Setup[claude-guidance/setup-instructions.md]
    CheckStage --> |Ongoing Project| Map[claude-guidance/map.md]

    Setup --> FolderMaps[Folder-Specific Maps]
    Map --> FolderMaps

    FolderMaps --> |src/| SrcMap[src/map.md]
    FolderMaps --> |docs/| DocsMap[docs/map.md]
    FolderMaps --> |tests/| TestsMap[tests/map.md]
    FolderMaps --> |Other| CustomMaps[Custom Folder Maps]

    SrcMap --> Work[Begin Task Execution]
    DocsMap --> Work
    TestsMap --> Work
    CustomMaps --> Work

    Work --> Context[Full Context Available]

    style Start fill:#9C27B0,stroke:#6A1B9A,color:#fff
    style RepoLevel fill:#4CAF50,stroke:#2E7D32,color:#fff
    style CheckStage fill:#FF9800,stroke:#E65100,color:#fff
    style Context fill:#4CAF50,stroke:#2E7D32,color:#fff
```

## Context Layers

```mermaid
graph LR
    subgraph "System Level"
        A[~/CLAUDE.md<br/>Global User Context]
    end

    subgraph "Repository Group"
        B[~/repos/CLAUDE.md<br/>Repos Directory Context]
    end

    subgraph "Project Level"
        C[Project/CLAUDE.md<br/>Project-Specific Context]
    end

    subgraph "Guidance Layer"
        D[claude-guidance/<br/>Setup & Workflow Docs]
    end

    subgraph "Folder Level"
        E[Folder Maps<br/>Directory-Specific Context]
    end

    A --> B
    B --> C
    C --> D
    D --> E

    style A fill:#E91E63,stroke:#880E4F,color:#fff
    style B fill:#9C27B0,stroke:#4A148C,color:#fff
    style C fill:#673AB7,stroke:#311B92,color:#fff
    style D fill:#2196F3,stroke:#0D47A1,color:#fff
    style E fill:#009688,stroke:#004D40,color:#fff
```

## Setup vs. Ongoing Project Flow

```mermaid
flowchart TD
    Agent[AI Agent Reads CLAUDE.md] --> Check{Check Codebase<br/>Status}

    Check --> |Empty/Minimal| NewProj[New Project Path]
    Check --> |Files Exist| OngoingProj[Ongoing Project Path]

    NewProj --> SetupDoc[Read: claude-guidance/<br/>setup-instructions.md]
    SetupDoc --> CreateStructure[Create Directory Structure]
    CreateStructure --> CreateMaps[Create Folder Maps]
    CreateMaps --> InitCode[Initialize Code]

    OngoingProj --> MapDoc[Read: claude-guidance/<br/>map.md]
    MapDoc --> UnderstandStructure[Understand Existing Structure]
    UnderstandStructure --> ReadMaps[Read Relevant Folder Maps]
    ReadMaps --> WorkOnCode[Work on Existing Code]

    InitCode --> Ready[Ready to Collaborate]
    WorkOnCode --> Ready

    style Agent fill:#4CAF50,stroke:#2E7D32,color:#fff
    style Check fill:#FF9800,stroke:#E65100,color:#fff
    style NewProj fill:#2196F3,stroke:#1565C0,color:#fff
    style OngoingProj fill:#9C27B0,stroke:#6A1B9A,color:#fff
    style Ready fill:#4CAF50,stroke:#2E7D32,color:#fff
```

## Key Principles

1. **Hierarchical Inheritance**: Context flows from global → repository group → project → folder level
2. **Stage-Aware Branching**: Different guidance paths for setup vs. ongoing development
3. **Distributed Context**: Folder maps provide localized context where needed
4. **Progressive Disclosure**: AI agent loads only relevant context for current task