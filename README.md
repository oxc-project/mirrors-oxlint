# mirrors-oxlint

This repository is a [pre-commit](https://pre-commit.com/) mirror for the npm package `oxlint`.

It is not the source code for `oxlint`.  
Its job is to publish and maintain the files/tags needed so users can run `oxlint` via `pre-commit`.

## How it works

- `.github/workflows/main.yml` runs `pre-commit-mirror-maker` on pushes to `main`.
- `.pre-commit-hooks.yaml` defines the hook metadata (`id`, `entry`, dependency version, file types).
- `.version` stores the currently mirrored package version.

The workflow regenerates mirror content and pushes updates (including tags) back to this repository.

## Updating

When a new `oxlint` release should be mirrored:

1. Update `.version` to that npm version.
2. Keep `.pre-commit-hooks.yaml` `additional_dependencies` aligned with the same version.
3. Push to `main` to run the workflow.
