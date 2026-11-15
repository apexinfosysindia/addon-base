# ApexOS App: Base Images

Docker base images for ApexOS apps.

## About

These are the base images used by ApexOS apps. They contain:

- [s6-overlay][s6] as a process supervisor.
- `jq` & `curl`, since every app uses them.
- A helper library: [Bashio][bashio].
- A template helper: [tempio][tempio].
- Log handling, app startup banners and update notifications.

## Usage

Apps build `FROM` the published base image:

```text
ghcr.io/apexinfosysindia/addon-base:19.0.0
```

The app store's root `build.yaml` pins this image for every
architecture; individual apps inherit it through their `build_from`
configuration.

## Provenance

This repository is pipeline output of the ApexOS build pipeline
(`apexinfosysindia/build-pipeline`): a transformed, debranded fork of an
upstream app base-image tree. Upstream ref, SHA and packaging details
are recorded in `.apexos/provenance.yaml` — never hand-edit pipeline-owned
surfaces (`.apexos/**`, `.github/workflows/apexos-*.yml`).

## License

MIT — see [LICENSE.md](LICENSE.md). Upstream copyright is retained.

[bashio]: https://github.com/apexinfosysindia/bashio
[s6]: https://github.com/just-containers/s6-overlay
[tempio]: https://github.com/apexinfosysindia/tempio
