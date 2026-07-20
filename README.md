# ApexOS Add-on: Base Images

Docker base images for ApexOS add-ons.

## About

These are the base images used by ApexOS add-ons. They contain:

- [s6-overlay][s6] as a process supervisor.
- `jq` & `curl`, since every add-on uses them.
- A helper library: [Bashio][bashio].
- A template helper: [tempio][tempio].
- Log handling, add-on startup banners and update notifications.

## Usage

Add-ons build `FROM` the published base image:

```text
ghcr.io/apexinfosysindia/addon-base:15.0.4
```

The add-on store's root `build.yaml` pins this image for every
architecture; individual add-ons inherit it through their `build_from`
configuration.

## Provenance

This repository is pipeline output of the ApexOS build pipeline
(`apexinfosysindia/build-pipeline`): a transformed, debranded fork of an
upstream add-on base-image tree. Upstream ref, SHA and packaging details
are recorded in `.apexos/provenance.yaml` — never hand-edit pipeline-owned
surfaces (`.apexos/**`, `.github/workflows/apexos-*.yml`).

[bashio]: https://github.com/apexinfosysindia/bashio
[s6]: https://github.com/just-containers/s6-overlay
[tempio]: https://github.com/apexinfosysindia/tempio
