# PRO4500 LightCrafter Control

Shared LightCrafter 4500 / DLPC350 control source used as a Git submodule by
the PRO4500 Android-camera and UV-camera control projects.

This repository contains the common light-engine control layer, including:

- DLPC350 command/API sources
- DLPC350 USB transport sources
- LightCrafter 4500 GUI resources
- bundled HIDAPI source used by the control builds

Project-specific camera synchronization code stays in the parent repositories.
Use this repository for changes that should apply to both PRO4500 control
systems.

## Submodule Usage

Parent repositories include this repository at `GUI/`.

Clone parent repositories with submodules:

```bash
git clone --recurse-submodules <parent-repo-url>
```

Initialize submodules after an existing clone:

```bash
git submodule update --init --recursive
```

After changing this repository, update the parent repository's `GUI` submodule
pointer and commit that parent change.
