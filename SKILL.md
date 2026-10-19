---
name: stream-branching
description: Determine branch bases and integration boundaries when independent implementation streams integrate individual plan pull requests through stream branches before a stable branch.
---

# Stream Branching

Use this skill when a repository develops independently completable implementation streams and integrates each stream into its stable branch after its individual implementation plans are complete.
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
- Allow direct dependencies among plans within a stream. Treat shared files and compatible use of established contracts as concurrency concerns rather than dependencies by themselves.
- Use results integrated into the stable branch as prerequisites from earlier phases. Use results integrated into the stream branch as prerequisites within that stream.

## Validate integration

- Validate plan pull requests according to their affected scope and the repository's existing test policy.
- Require end-to-end verification of the completed stream on its integration pull request to the stable branch. If the stable branch advances in a way that affects this candidate, incorporate those changes and verify the updated candidate.
- Treat the completed stream as established on the stable branch after the integration pull request is merged.

This skill owns the stream-level integration strategy, not the mechanics of Git, pull requests, or CI configuration.
