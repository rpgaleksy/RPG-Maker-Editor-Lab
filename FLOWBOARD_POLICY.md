# Flowboard Project Status Policy

Policy revision: 2026-09-13

## Purpose and authority

Flowboard is an optional, read-only visualization of a project's current state.
This policy applies only when it is present as `FLOWBOARD_POLICY.md` in an
explicitly selected repository and its `FLOWBOARD_POLICY.addendum.md` is
configured. Project type and Flowboard use elsewhere do not opt a repository in.

`AGENTS.md` governs authorization, ownership, review, completion, commits, and
external actions. The configured tracker, accepted decisions, current technical
documentation, and verified repository evidence remain authoritative. Flowboard
is a compact projection of those sources, never another tracker.

This policy authorizes updates only to the configured Flowboard project file. It
does not authorize changing its sources, committing, publishing, deploying,
writing another repository, contacting services, or fetching external data.

## Configuration and data contract

The addendum selects one integration state:

- `planned`: configuration and a validated draft may be prepared, but the view
  is not maintained or presented as current;
- `active`: the project file is the current projection and follows its configured
  update mode;
- `paused`: preserve the view without updating it and present it as potentially
  stale;
- `disabled`: do not update, synchronize, render as current, or remove Flowboard
  files without a separate user instruction.

The default tracked source is `.flowboard/project.json`. It contains one project
and declares the schema version. The canonical machine-readable schema belongs
to the Flowboard tool and defines exact fields, types, enums, localization,
relationships, and compatibility. Do not invent project-specific structure or
silently migrate an unsupported version.

Use stable, unique IDs for projects, stages, modules, work items, and optional
cross-cutting lanes. Preserve identity across wording, translation, ordering,
and movement. Ordered stages form the primary display flow; lanes may reference
existing modules without duplicating their state or counts.

Optional relations may project material `requires`, `informs`, and `feedback`
paths between existing IDs. `requires` is blocking and must remain acyclic;
`informs` and `feedback` are non-blocking, and feedback may return to earlier
completed work. Relations neither change status automatically nor replace
tracker data.

## Projection semantics

Use these lifecycle states:

- `queued`: accepted or plausible later work;
- `active`: work currently in progress or the accepted current focus;
- `blocked`: work stopped by a named dependency, decision, permission, resource,
  or evidence gap;
- `review`: work awaiting required review or acceptance;
- `done`: work satisfying applicable acceptance, review, validation, and durable
  integration requirements.

Record work kind separately when useful: `research`, `design`, `implementation`,
`validation`, `documentation`, or `release`. For example, an ongoing
investigation is `status: active` and `kind: research`.

Do not infer completion from assignment, a commit, a successful build, or time
elapsed. Apply the active `AGENTS.md` completion rules and reflect accepted
evidence regardless of which authorized task performs the reconciliation. A
module marked `done` must not contain unresolved work that belongs to its stated
displayed scope; report contradictions rather than hiding or recalculating them.

Show concise, stakeholder-readable stages, modules, work items, evidence
summaries, current focus, and next gate. Link or name authoritative records where
useful without copying their full history. Preserve uncertainty and distinguish
verified results, open investigation, and future plans.

Progress is the calculated count of unique visible work items, normally
`done / total`. It is not a forecast, effort estimate, confidence score, or
percentage of all possible work. Localize all configured stakeholder-visible
text while keeping IDs and established product names stable.

## Updating Flowboard

The default mode is `user-requested`. An instruction such as “Update Flowboard to
the current verified project state” authorizes one bounded reconciliation:

1. Read the addendum and current authoritative sources.
2. Compare them with the existing projection; update only relevant structure,
   state, focus, gates, evidence summaries, and the actual reconciliation time.
3. Preserve stable IDs and unresolved uncertainty. Do not reconstruct state from
   chat or invent missing conclusions.
4. Validate against the canonical schema and semantic checks, render the local
   view, inspect the diff, and report changes and unresolved conflicts.
5. Follow `AGENTS.md` for any commit proposal or authorized commit.

The addendum may instead select `meaningful-boundaries`. This updates Flowboard
when visible work starts, blocks, resumes, enters or passes review, or completes;
when a material decision changes scope or structure; or when focus, the next
gate, a milestone, or supporting evidence materially changes. A commit alone is
not a trigger.

In a shared-workspace team, only the current write owner may edit the Flowboard
source. Any authorized reconciler may record a state already supported and
accepted under the project's normal rules.

## Local viewer and Git freshness

The local interface may navigate, filter, and summarize projects but must not
persist task or status changes. A future write adapter requires separate design,
configuration, and user approval.

The viewer reads only explicitly registered repository roots and their fixed
Flowboard files. It may perform bounded, read-only Git queries inside those
repositories to derive the last commit affecting the Flowboard source, current
HEAD, commit times, comparable commit distance, and uncommitted state. It must
not accept arbitrary request paths, scan unrelated files, run repository code,
fetch remotes, or follow paths outside registered roots.

Store the actual reconciliation time in the project file. Do not manually store
current commit IDs or commit distance. Git freshness is derived equally for
commits made by Codex, GitHub Desktop, or another Git client. Show uncommitted,
unavailable, or divergent state explicitly. Commit distance is only a freshness
hint and does not prove that the projection is correct or stale.

Track the project file by default. Include its update in the related commit
proposal or authorized commit when practical; a substantial standalone
reconciliation may use a documentation commit. Generated navigation data and
previews are non-authoritative outputs and should not be tracked without a
documented delivery reason.

## Sharing boundary

Treat project data as local/internal by default. Do not publish or synchronize it
merely because the viewer can read it. Any later stakeholder export must be
separately approved, omit secrets, local paths, private records, and unapproved
claims, and carry project ID, schema version, source revision, and export time.
Hosted delivery and access control are governed by the destination's
`WEB_POLICY.md` and addendum.

User-approved policy changes apply once read. A later commit records the durable
transition but does not reinterpret earlier project state.
