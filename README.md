# Sicht Language Package Registry

This repository hosts the package index and immutable versioned archives for [Sicht Language](https://github.com/gothardener/sichtlang).

## Install a package

```sh
sicht install mathx@1.0.0
```

The package manager uses the exact package version and verifies the archive's SHA-256 checksum before installing. Dependencies are not resolved or installed automatically.

## Registry format

Each `[[package]]` entry in `registry.toml` includes a package name, exact version, description, immutable archive URL, and SHA-256 checksum. Archive URLs should point to a commit-pinned raw file or another immutable release asset. Never replace an archive for an already-published version.

## Publishing

1. Add the versioned ZIP under `packages/<name>/<version>.zip`.
2. Compute its SHA-256 checksum.
3. Commit the archive first, then use that commit SHA in the raw archive URL in `registry.toml`.
4. Add or update the package entry and submit a pull request.

Archives must contain `sicht.toml` and `main.si` at their ZIP root.
