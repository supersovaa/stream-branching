# Stream Branching

A lightweight skill for repositories that develop multiple independently completable implementation streams, with individual implementation-plan pull requests integrated into a stream branch before the whole stream is merged into the stable branch.

## When to use

Install and activate `stream-branching` for development that explicitly uses stream-level integration branches. It determines the branch hierarchy, plan-to-stream pull-request bases, cross-stream dependency boundary, and stream-completion verification boundary.

Ordinary repositories and work that do not use stream-level integration continue to use the existing branch and pull-request rules, such as targeting `main` or `master`. No changes to `codex-web-workflow`, `plan-driven-implementation`, or `ci-efficiency` are necessary to enable that ordinary mode.

## Install

Install this repository's `SKILL.md` as the `stream-branching` skill using the target agent's skill installation mechanism. In repositories adopting stream-based development, route stream planning and integration work to the installed skill through the repository's agent guidance.

## Responsibility boundaries

- `stream-branching`: stream-level branch hierarchy, integration targets, cross-stream dependency boundary, and completed-stream verification requirement.
- Existing Git / PR workflows (including [`codex-web-workflow`](https://github.com/supersovaa/codex-web-workflow)): select names and perform Git, push, and pull-request operations with the resolved branch roles.
- Existing implementation planning workflows (including [`plan-driven-implementation`](https://github.com/supersovaa/plan-driven-implementation)): determine plan contents, direct dependencies, plan state, and completion evidence.
- Existing CI workflows (including [`ci-efficiency`](https://github.com/supersovaa/ci-efficiency)): determine actual test execution, affected-scope selection, and CI configuration.

See [SKILL.md](SKILL.md) for the rules.
