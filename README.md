# mirrors-oxlint

This repository is a [pre-commit](https://pre-commit.com/) mirror for the npm package `oxlint`.

It is not the source code for `oxlint`.  
Its job is to publish and maintain the files/tags needed so users can run `oxlint` via `pre-commit`.

## How it works

- `.github/workflows/main.yml` runs `pre-commit-mirror-maker` on pushes to `main` and opens a mirror update PR.
- `.pre-commit-hooks.yaml` defines the hook metadata (`id`, `entry`, dependency version, file types).
- `.version` stores the currently mirrored package version.

The workflow regenerates mirror content, pushes missing tags, and opens an auto-merge PR for mirror updates.

## Updating

When a new `oxlint` release should be mirrored:

1. Update `.version` to that npm version.
2. Keep `.pre-commit-hooks.yaml` `additional_dependencies` aligned with the same version.
3. Push to `main` to run the workflow and open the mirror update PR.

# [Sponsored By](https://oxc.rs/sponsor)

<p align="center">
  <a href="https://oxc.rs/sponsor">
    <img src="https://raw.githubusercontent.com/oxc-project/sponsors/main/sponsors.svg" alt="Our sponsors" />
  </a>
</p>
