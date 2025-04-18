---
status: Decided
date: 2024-12-23
decision-makers: "@LarsKemmann"
discussion: https://github.com/CoeptLLC/coept-engineering-system/discussions/1
---

# Documenting Decisions

## Context and Problem Statement

A well-maintained record of the system's evolution provides two things:
1. a consistent understanding of, and appreciation for, the structure of the system by all existing team members, and
2. a starting point for onboarding all new team members to the same level of understanding.

Most software engineering teams approach system documentation in an ad-hoc, after-the-fact manner. Such inconsistent documentation practices create serious gaps in team members' understanding of the decisions made in the development of the system. Those gaps in understanding inevitably produce inconsistent adherence to the decisions, and that inconsistency makes it impossible for the software engineering team to maintain quality.

> ### ❓ Problem Statement
> 
> How might we ensure consistency in documenting decisions, across both the engineering system and any systems built using the engineering system?

## Considered Options

* **External documentation** in a collaboration environment like Teams/SharePoint
* **Markdown documentation** as part of the repository, perhaps using a documentation site generator or the GitHub or Azure DevOps wiki structure
* **Architecture Decision Records**, as defined by [the ADR GitHub organization](https://adr.github.io/), which implement a consistent structure and requirements for the Markdown documentation as part of the repository

## Decision Outcome

Chosen option: **Architecture Decision Records**, because:
1. colocating the decision documentation with the code in the repository is essential to making the documentation discoverable and accessible, and
2. adopting a standard practice for documenting decision records provides a baseline for consistency in continuous documentation (i.e., having good documentation from the beginning raises the bar and helps to set a clear expectation of continued good documentation).

## Guidance

- Team members MUST document **all** agreed-upon system decisions using architecture decision records (ADRs).
- ADRs belong in the `docs/decisions` folder. Specifically, the `docs/decisions/ces` folder MUST be used only by the underlying engineering system, to prevent merge conflicts if a system chooses to forward-integrate engineering system updates into the system. Likewise, the `docs/decisions/system` folder SHOULD be used to contain all ADRs specific to a particular system that is built on the engineering system.
- Each architecture decision record MUST include the following sections at a minimum:
  - Metadata, as demonstrated in this ADR file, MUST include:
    - `status`: `Pending`, `Decided`, `Superseded`, etc.
    - `date`: decision date, in `yyyy-MM-dd` format
    - `decision-makers`: names or usernames of the decision makers involved
    - `discussion`: a link to the archived discussion thread
  - Context and Problem Statement
  - Considered Options
  - Decision Outcome
- An ADR MAY include a "Guidance" section to further explain how a decision is to be implemented.
- Team members SHOULD use the ADR templates provided by [the Markdown Architectural Decision Records project v4.*](https://github.com/adr/madr/tree/4.0.0) unless a particular decision requires a different template.
- Team members MAY use local (development-time) ADR support tooling of their choice, such as [MADR](https://adr.github.io/madr/) or [dotnet adr](https://github.com/endjin/dotnet-adr).
