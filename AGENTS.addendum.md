# Project Addendum

This file records project facts and user-approved overrides of the active `AGENTS.md`. Keep only relevant, completed sections. Do not repeat shared policies or keep a work log here.

Overrides apply only to settings the active `AGENTS.md` defines and permits changing. Skip workflow/override sections unsupported by it; they do not introduce new workflows or permissions. Project facts and existing requirements still apply within their stated scope. Blank fields and placeholders grant nothing. Record existing requirements, not invented rules. Put policy-specific settings in that policy's own addendum.

## Project

```text
Name and purpose: RPG Maker Editor Lab; research and prototypes for an RM2000-/RM2003-compatible editor on Apple Silicon.
Architecture and deliverables: No editor is implemented and no implementation basis has been selected. A native solution is the long-term goal; a Windows editor under CrossOver or in a VM may be used for comparison and as a temporary working tool.
Key documentation paths: README.md; VERSIONING.md; docs/references.md; docs/investigation.md; docs/next-task-prompt.md
Relevant paths and their purpose: ../RPG-RT-Apple-Silicon/ is the separate native EasyRPG runtime repository and a read-only reference/test target; ../Editor Reference Material/RPG Maker 2003/ contains the user-provided complete Steam installation, including subdirectories rather than only the editor executable; ../Editor Reference Material/RPG Maker 2009 Ultimate/ contains external original packages; within commissioned scope, ../Editor Reference Material/analysis/ may contain local working copies, Ghidra projects, and generated analysis output outside this repository; ../Add-ons and Patches/, ../../archive/, and ../../games_archive/ are read-only references; build/upstream/ is reserved for pinned open-source dependencies; build/, dist/, and test-output/ are ignored generated working directories.
Scope and authoritative sources: Active development is confined to this repository. Original file formats, EasyRPG extensions, and Windows patches must be assessed separately. Successful startup alone does not establish full compatibility.
Existing project requirements: Preserve all externally supplied originals. Do not casually execute third-party Windows programs. Do not add proprietary editor programs, DLLs, RTP, game assets, or extracted/decompiled third-party content to this repository, including ignored paths; keep only original tools, factual findings, and source documentation here. Open-source dependencies may be obtained under build/upstream/, but record the source, commit/version, license, and local changes before integration. Use self-created synthetic test projects. Inspect external games only without modification; the user supplies additional games. Do not use symlinks to evade these boundaries. Work autonomously in small verifiable steps, avoid routine approval loops, preserve unrelated changes, and distinguish results, assumptions, and open questions.
```

## Commands and completion

```text
Setup: Read README.md, VERSIONING.md, the applicable policy files/addenda, and `git status --short --branch` before work.
Build: No build exists yet.
Tests: No automated tests exist yet. Run relevant tests/builds once available and document the results.
Lint/format: No project-specific lint or format command is currently configured.
Manual checks: For documentation-only changes, inspect content and the complete diff, check links as applicable, and run `git diff --check`. Before every authorized commit, run `git status --short --branch`, inspect the complete `git diff --cached` including new files, and run `git diff --cached --check`; repeat after any staging change, then inspect repository status after the commit.
Intended integration branch or checkout: unverified; current checkout is main
```

## Approved overrides

```text
Setting: Local staging and commits
Project value: Completed project work may be staged selectively and committed locally without a routine approval loop. Use English Conventional Commits and the active AGENTS.md attribution format. Preserve unrelated work. No pushes, tags, releases, history rewrites, publication, or deployment are authorized by this grant.
Scope or duration: Ongoing repository work, unless a task gives narrower instructions. A task that explicitly prohibits staging or commits remains controlling for that task.
User approval and reason: Migrated from the repository's pre-rollout root AGENTS.md, which required autonomous local commits for completed steps.
```

## Existing team tasks

```text
Role: Astra — Technical Lead
Task: Astra — Technical Lead: 01a09d23-7713-7842-acb6-4d8db85bad72

Role: Sol — Senior Engineer
Task: Sol — Senior Engineer: 01a09d24-5412-70c3-8a59-a161510001aa

Role: Luna — Implementation Engineer
Task: Luna — Implementation Engineer: 01a09d24-a1c8-7072-8048-a2f9e642c18d

Terra mode: consultant
Terra task: Terra — Workflow Consultant: 01a09d25-0161-7550-8d02-27434fbf8f9e
```

Communication mode remains manual. Terra may advise on priorities and routing and draft handoffs, but must not contact tasks or act as coordinator. Task identifiers do not authorize contact.
