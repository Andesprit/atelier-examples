# Flow Atelier examples

This repository is a browsable catalog of public
[Flow Atelier](https://github.com/Andesprit/flow-atelier) conduit packages and
examples maintained by Andesprit. Each catalog entry remains an independent
repository with its own history, releases, documentation, and installation
path.

## Important: install child repositories directly

The entries below are Git submodules pinned to known commits for browsing.
Flow Atelier's `atelier add` command does not recurse into submodules or load
package manifests from nested directories. Therefore:

- Do **not** use `atelier add Andesprit/atelier-examples`.
- Install the package you want directly with the command in the catalog.

## Catalog

| Path | Repository | What it demonstrates | Install |
| --- | --- | --- | --- |
| [`autonomous-projects/`](autonomous-projects/) | [Andesprit/autonomous-projects](https://github.com/Andesprit/autonomous-projects) | A scheduled improvement loop that proposes ideas and reviews, then implements approved tasks behind an independent review gate. | `atelier add Andesprit/autonomous-projects` |
| [`project-pipeline/`](project-pipeline/) | [Andesprit/project-pipeline](https://github.com/Andesprit/project-pipeline) | A braindump-to-plan-to-implementation pipeline with human approval gates and application review. It depends on `autonomous-projects`; install that package first. | `atelier add Andesprit/project-pipeline` |
| [`pursue-goal-and-review/`](pursue-goal-and-review/) | [Andesprit/pursue-goal-and-review](https://github.com/Andesprit/pursue-goal-and-review) | A focused build-and-review loop: one agent performs the task and another independently verifies completion. | `atelier add Andesprit/pursue-goal-and-review` |
| [`sdlc-atelier/`](sdlc-atelier/) | [Andesprit/sdlc-atelier](https://github.com/Andesprit/sdlc-atelier) | Two minimal SDLC conduits. `spec-plan-build` remains a useful small example; `goal` is superseded by `pursue-goal-and-review`. | `atelier add Andesprit/sdlc-atelier` |

`pursue-goal-and-review` and `sdlc-atelier` currently have no
`atelier-package.yaml`. Flow Atelier can discover their conduit directories,
but emits a warning during installation.

## Browse locally

Clone the catalog and initialize every pinned repository:

```bash
git clone --recurse-submodules https://github.com/Andesprit/atelier-examples.git
```

If the catalog was cloned without submodules:

```bash
git submodule update --init --recursive
```

Submodules intentionally pin exact commits. Maintainers can fetch the configured
`main` branches with `git submodule update --remote`, review the resulting
changes, and commit the new pins.

## Install Flow Atelier

Install the workflow runner before installing any conduit package:

```bash
uv tool install flow-atelier
atelier --version
```

See [Andesprit/flow-atelier](https://github.com/Andesprit/flow-atelier) for the
CLI, conduit format, harness setup, scheduling, and server documentation.

## Scope

This catalog contains public, reusable conduit examples. The Flow Atelier
engine is linked as a dependency rather than embedded as a submodule. No child
source is copied into this repository.
