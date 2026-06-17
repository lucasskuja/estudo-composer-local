# cloud-composer-local-reference

Reference repository for local Cloud Composer development, packaging a reusable repository structure around Google's `composer-local-dev` workflow.

## What This Repository Is

This repository provides a practical reference setup for engineers who want to run and organize local Cloud Composer development with a cleaner, reusable project structure.

It is designed to serve as:

- a reference implementation for local Composer-based development setup
- a reusable repository template for future data platform work
- a starting point for extending local Airflow and Cloud Composer workflows

## What This Repository Is Not

This repository does not reimplement Cloud Composer locally from scratch.

Instead, it builds on the upstream Google project [`composer-local-dev`](https://github.com/GoogleCloudPlatform/composer-local-dev), which is included here as a Git submodule and remains the execution base for the local environment.

## Current Scope

Today, the repository delivers:

- a versioned wrapper around the upstream `composer-local-dev` project
- a stable entry point for local Cloud Composer experimentation and extension
- repository-level documentation that clarifies setup intent and reuse boundaries

This means the main value of the repository is its framing as a reusable reference asset, not a custom orchestration framework or a full platform implementation.

## Use Cases

This repository is useful when you want to:

- establish a repeatable local Cloud Composer starting point
- keep the upstream local runtime pinned through a submodule
- reuse the same setup pattern across future Composer-oriented projects
- provide a documented baseline before adding DAGs, plugins, configuration, or project-specific automation

## Repository Structure

```text
.
|-- README.md
|-- CONTRIBUTING.md
|-- .gitmodules
`-- composer-local-dev/   # Upstream Google Composer local development project (submodule)
```

## Architecture Approach

The repository follows a thin-wrapper approach:

- Google provides the local execution environment through `composer-local-dev`
- this repository provides the reusable container for documentation, version pinning, and future project extensions
- downstream work can add DAGs, config, helper scripts, and project conventions without losing the upstream reference point

## Prerequisites

- Python 3.8 or later
- [Google Cloud CLI](https://cloud.google.com/sdk/docs/install)
- [Docker](https://www.docker.com/)
- At least 8 GB of machine memory recommended, 16 GB preferred
- At least 4 GB allocated to Docker, 8 GB preferred

## Getting Started

1. Clone this repository:

```bash
git clone https://github.com/lucasskuja/cloud-composer-local-reference.git
```

2. Move into the repository root.

3. Initialize the submodule:

```bash
git submodule update --init --recursive
```

4. Optionally create and activate a Python virtual environment before running any local setup commands.

Linux:

```bash
python -m venv venv
source venv/bin/activate
```

Windows PowerShell:

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

5. Follow the upstream Composer local setup instructions from Google:

- [composer-local-dev setup guide](https://github.com/GoogleCloudPlatform/composer-local-dev/blob/eacc17c2c934b7873b7302f4d6b2dd9bdaf6d9d8/README.md#configure-credentials)

## Relationship To The Upstream Project

The `composer-local-dev` directory is a submodule pointing to the official Google Cloud project.

This repository intentionally keeps that dependency explicit so it can:

- preserve a known upstream reference
- document a reusable adoption pattern
- provide a clean place for future extensions without mixing them into the upstream source

## Extension Points

Typical next steps for evolving this repository into a broader internal or client-facing template include:

- adding project-specific DAGs
- organizing local configuration and environment conventions
- introducing helper scripts for bootstrap and validation
- documenting reusable patterns for Airflow-based data workflows

## Limitations

At the current stage, this repository does not include:

- custom DAG implementations
- opinionated environment automation beyond the upstream tooling
- project-specific plugins, operators, or infrastructure modules

Those additions can be layered on top of this reference structure as needed.

## Contributing

Contribution guidelines are available in [CONTRIBUTING.md](C:\Users\Trabalho\Documents\repositorios\pessoal\estudo-composer-local\CONTRIBUTING.md).

## References

- [Google Cloud Composer local development documentation](https://cloud.google.com/composer/docs/composer-2/run-local-airflow-environments)
- [GoogleCloudPlatform/composer-local-dev](https://github.com/GoogleCloudPlatform/composer-local-dev)
