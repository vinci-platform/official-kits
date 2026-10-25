# Vinci Official Kits

Official, pre-rendered design kits for Vinci content authoring, distributed for
Vinci Studio.

> **Status: pre-release.** The kit format is still a draft and no kit has been
> published yet. `index.json` is intentionally empty.

## What a kit is

A kit is the released form of one official material, for example a face button
in a given finish. Each colour channel is rendered once per colour as a separate
PNG layer. Vinci Studio stacks the layers for the author's choices and writes an
ordinary Vinci Skin source, so content built from kits needs nothing special at
runtime.

## How kits are distributed

- **Versions live in GitHub Releases, not in Git.** Each kit version is one
  release, tagged `<kit-id>@<version>` (for example
  `face-button.candy-gel@1.0.0`). Its assets are the kit archive, its SHA-256
  checksum and its signature. Releases are never edited after publication. A
  fix is a new version.
- **`index.json` is the catalog.** It lists every published kit version with its
  download URL, size, SHA-256 and signature. Vinci Studio reads this file to
  discover kits. It downloads only the versions an author pins, and upgrades only
  when the author chooses to.
- **Verification.** Studio verifies every archive's checksum and signature
  before use, and verifies each layer's SHA-256 against the kit manifest.

## Repository rules

- Only small text files are committed: this README, the license, the catalog and
  format documentation. Images and archives never enter Git history.
- `main` is protected. Changes, including catalog updates made by the release
  automation, go through pull requests.
- Kits are produced by the Vinci team's internal pipeline. Issues are welcome;
  pull requests that add or change kit artwork are not accepted.

## License

Code, documentation and kit artwork in this repository and its releases are
available under the [MIT License](LICENSE) unless a kit states otherwise in its
own notice.
