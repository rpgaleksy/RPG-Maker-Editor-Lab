# Product Versioning Guideline

## Scope

Product versions mark meaningful, reproducible milestones—not commits, compilations, work sessions, or elapsed time.

This file governs product versions and build artifacts only. `AGENTS.md` governs commit boundaries, messages, staging, and commits; this file grants no Git authorization. One product version may span several commits.

Keep commits, preview builds, product versions, and development logs distinct. Also separate schema, data-format, model, or platform identifiers when they have independent compatibility requirements.

## Project configuration

```text
Product: RPG Maker Editor Lab
Developer or vendor display name: undecided
Stable product or vendor identifiers: undecided
Authoritative version source: deferred: first executable prototype; then root VERSION containing the full SemVer string, initially 0.1.0-dev
Derived version locations: deferred: introduction of product or package metadata
Platform build identifier: none until technically required
Preview artifact: deferred: first preview build
Milestone artifact: deferred: first preserved milestone build
Changelog: deferred: first functional state; then CHANGELOG.md with an Unreleased section
Development log: undecided
Adoption baseline: legacy guideline introduced in commit 35f65e2 on 2026-09-12; current merged guideline: deferred: first commit containing this policy
```

- Confirm the user-facing product and developer/vendor names; do not invent placeholders. Inspect stable host/platform identifiers before changing them and preserve established values unless a deliberate migration is approved.
- Mark unresolved fields `undecided` or `deferred: <trigger>`; they block only actions that depend on them.
- The authoritative source must represent the full product version. Derived display or package locations must match it or use a documented deterministic mapping when their format cannot encode it; do not duplicate the current value in this file.
- If a platform requires or the project uses an independent build identifier, keep it separate; otherwise record `none`.
- Define artifact paths, durable records, and the commit, date, or legacy version from which this policy applies. Read the current version from its source and existing tags.

### Defaults

Unless explicitly overridden by the project configuration or user:

- developer/vendor display name: `ecklaedle Audio`;
- maturity: `dev`;
- new-project version source: root `VERSION` containing the full SemVer string;
- preview artifacts: `builds/previews/<timestamp>/`;
- milestone artifacts: `builds/milestones/v<version>/`;
- changelog: `CHANGELOG.md`;
- development log: `docs/development-log.md`, unless an existing ADR or decision-history system serves the same purpose;
- independent platform build identifier: `none` until technically required;
- adoption baseline: the first commit containing the configured policy, unless an earlier exposed version or legacy boundary is explicitly documented.

Do not apply these defaults over an established authoritative source or technical identifier. If stable product, vendor, bundle, plugin, signing, or platform identifiers are not already established, mark them `undecided` or `deferred: <trigger>` until deliberately assigned.

### Retained project settings

- The project has no product version yet. Introduce the configured root `VERSION` only with the first executable in-house prototype, starting at `0.1.0-dev`. Record upstream versions separately.
- Preserve the existing authorization for autonomous local version maintenance and local commits under `AGENTS.addendum.md`. This replaces only the candidate workflow's separate approval requirement for preparing, staging, and committing local version metadata. It does not authorize milestone artifact compilation or promotion, pushes, tags, releases, publication, or deployment.
- Do not create a product version for every commit or verification build. Relate builds to the product version, Git commit, and dirty working-tree state as applicable.
- During `0.x`, incompatible changes increment `MINOR` and must be explained. Declare `1.0.0` only after the stable functional scope has been explicitly agreed.

## Version scheme and maturity

Use Semantic Versioning: `MAJOR.MINOR.PATCH`.

Before `1.0.0`:

- `0.MINOR.0`: new coherent, demonstrable milestone;
- `0.MINOR.PATCH`: relevant correction or refinement of a preserved milestone;
- no bump: small fixes not worth preserving or distributing separately.

After `1.0.0`, increment `MAJOR` for incompatible changes, `MINOR` for compatible capabilities, and `PATCH` for compatible fixes. Declaring `1.0.0` requires an explicit user decision.

Maturity reflects the intended audience:

- `dev`: private development and internal previews;
- `alpha`: selected trusted testers; incomplete or breaking behavior remains possible;
- `beta`: broader testers after the main direction and capabilities are established;
- `rc`: release candidate with no planned feature changes;
- no label: released for its intended audience.

Number prereleases (`alpha.1`, `alpha.2`) only when preserving or distributing distinct test versions. Ordinary previews may share a label such as `0.5.0-dev`.

## Milestones and builds

A milestone should be coherent and worth preserving for comparison, documentation, testing, or release. It must produce a demonstrable result, pass the checks relevant to its scope, and become traceable to a specific commit when finalized.

A version string alone does not establish a finalized milestone; verify its tag, records, artifact provenance, and exposure.

Development speed and implementation size are irrelevant. Ordinary commits, compilations, previews, minor refinements, and unfinished experiments do not create versions. Preserve concept or specification work through commits and development logs unless the documentation itself is a versioned deliverable.

Separate previews from preserved milestones:

```text
builds/
  previews/260811_0441/Product.ext
  milestones/v0.5.0-alpha.1/Product.ext
```

Keep the artifact name stable when required by a host or operating system.

Create previews only when requested or useful for verification. They neither change the version nor require a changelog entry or tag. Reference a commit only if it exactly represents the preview; otherwise mark it `uncommitted`.

A preview may be promoted only when its exact provenance and candidate contents are verified; otherwise it cannot become the milestone artifact.

Codex may recommend a versioned milestone artifact but must obtain explicit approval to compile or promote it. Ordinary verification builds remain previews. Finalized versions, tags, and artifacts are immutable; use a new version for different contents.

If artifacts live outside Git, record their location. Do not claim that a tag reproduces an untracked binary exactly unless the build is reproducible.

## Candidate and finalization workflow

At a natural handoff, Codex may recommend exactly one version and, separately, one milestone build, with a brief reason. The user may accept, override, postpone, or decline either.

Approving a version authorizes only preparation of its candidate metadata. Building or promoting a milestone artifact, staging or committing, tagging, and creating, uploading, or publishing a GitHub Release each remain separately controlled as defined below and by the retained project settings.

### Candidate

After version approval, or under the retained authorization for autonomous local version maintenance:

1. update the authoritative source and derived locations;
2. update the changelog and development log as applicable;
3. compile or promote a milestone artifact only if separately approved;
4. validate the candidate;
5. prepare a diff-grounded commit message under `AGENTS.md`, and stage or commit only as authorized by `AGENTS.addendum.md`.

The candidate remains pending until an approved or otherwise authorized commit exists.

### Finalized milestone

After the approved commit exists, verify that it represents the candidate. Only on explicit request may Codex create the immutable tag `vMAJOR.MINOR.PATCH[-PRERELEASE]`, promote or archive its matching artifact, or update external milestone records. Finalization does not authorize a GitHub Release.

## GitHub Releases

A GitHub Release is a distribution event. Codex may report readiness but must not produce a release build, create or publish a release, upload assets, or mark a release as latest without an explicit request.

Before preparing one, verify as applicable:

- scope, audience, version, changelog, documentation, and compatibility notes agree;
- relevant automated, host, installation, and manual acceptance checks pass;
- no known issue blocks the intended use;
- the release build comes from the exact clean tagged commit;
- required signing, notarization, packaging, checksums, notes, and approved assets are complete.

When explicitly requested, finalize the milestone, verify or produce the approved build from the release commit, and prepare a draft for the immutable tag. Attach the approved notes and assets, and mark alpha, beta, or RC distributions as prereleases. Report the draft; publish only after explicit final approval.

## Milestone record

Record each version concisely:

```text
## v0.5.0-alpha.1 — YYYY-MM-DD

Goal:
Result:
Key decisions:
Known limitations:
Evidence:
Git commit or tag:
```

Evidence may include builds, screenshots, rendered output, audio comparisons, measurements, or demonstrations. Keep `CHANGELOG.md` product-focused. Use the development log for meaningful chronology: hypotheses, evidence, tradeoffs, decisions, and unsuccessful approaches that influenced later work. It may index existing ADRs or decision records; link instead of duplicating authoritative details. The log preserves history, not the current technical source of truth.

## Parallel-agent coordination

Use a single writer for product versioning. In parallel work, only the coordinating main agent may recommend or prepare a version change after integrating and verifying all relevant results.

Other agents may implement, inspect, test, or document independent workstreams, but must not reserve versions, edit the authoritative source, finalize records, create tags, or promote artifacts. Before preparing a version change, the coordinator must re-read the authoritative source, relevant tags and records, and the working tree, then resolve concurrent changes.

## Existing history

Before adoption, inspect existing version sources, derived metadata, tags, builds, records, and compatibility identifiers. Define a clear transition point and preserve useful legacy timestamps and names. Mark uncertain retrospective mappings `legacy` or `reconstructed`; do not invent precision or rewrite valid history for a cleaner timeline.

When legacy names and embedded metadata disagree, record both and mark the mapping `reconstructed`; do not rename the artifact merely to fit this policy.

User-approved policy changes govern subsequent work once read. Their commit records the durable transition but does not delay their effect or reinterpret earlier history.

Do not lower a version already exposed to hosts, saved projects, testers, or users without explicit approval and a compatibility assessment. Internal-only versioning may be reorganized with user approval if the historical mapping remains documented.
