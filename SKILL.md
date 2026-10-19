---
name: stream-branching
description: Plan or operate branch hierarchies that integrate individual implementation-plan pull requests into independent stream branches before stable-branch integration.
---

# Stream Branching

Use this skill when planning or operating a workflow that integrates implementation-plan pull requests into independent stream branches, then integrates completed streams into a stable branch.
This skill selects branch and integration boundaries. Existing repository workflows own branch names, Git operations, pull-request creation, plan execution, and CI test selection.

## Select integration branches

- Use the repository's existing stable branch as the final integration target.
- Create one integration branch for each independently completable stream from the stable branch. Keep parallel stream branches independent of one another.
- Create each plan's working branch from the current state of its stream branch, and target the plan's pull request at that stream branch.
- When a plan requires another plan's result, begin from the stream state containing the integrated prerequisite rather than an unmerged pull request.
- Target the completed stream's integration pull request at the stable branch. Work outside the stream workflow uses the repository's ordinary pull-request base rules.

## Keep parallel streams independent

- Within the same development phase, make different streams completable without depending directly on one another's unfinished results.
- Resolve a required cross-stream prerequisite during planning by establishing a shared contract in an earlier phase, assigning the responsibilities to one stream, or moving the consumer to a later phase.
- Allow direct dependencies among plans within a stream. Shared files or use of established contracts alone imply neither a direct dependency nor a concurrency conflict; evaluate concrete interference with the existing planning workflow.
- Use results integrated into the stable branch as prerequisites from earlier phases. Use results integrated into the stream branch as prerequisites within that stream.

## Validate integration

- Validate plan pull requests according to their affected scope and the repository's existing test policy.
- Require full end-to-end verification of the integrated system on the completed stream's pull request to the stable branch. If the stable branch advances in a way that affects this candidate, incorporate those changes and verify the updated candidate.
- Treat the completed stream as established on the stable branch after the integration pull request is merged.

This skill owns the stream-level integration strategy, not the mechanics of Git, pull requests, or CI configuration.
