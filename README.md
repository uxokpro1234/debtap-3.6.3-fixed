# debtap-cpp

A C++ port of [debtap](https://github.com/helixarch/debtap) that converts Debian `.deb` packages into Arch Linux `.pkg.tar.zst` packages.

## Build

```bash
g++ -std=c++17 -O2 -Wall -Wextra -pedantic debtap.cpp -o debtap
```

## Usage

```bash
./debtap package.deb
sudo pacman -U package-version-1-x86_64.pkg.tar.zst
```

## Options

- `-o DIR` — Set output directory.
- `--map FILE` — Specify a package-name mapping file.
- `-p` — Generate a PKGBUILD alongside the package.
- `-P` — Generate only a PKGBUILD.
- `-w` — Remove dependency version constraints.
- `-s` — Enable i386-to-x86_64 compatibility mode.
- `--keep-work` — Keep temporary files.
- `--namcap` — Check the generated package.
- `-f` — Overwrite existing output files.
- `-h` — Show help.

## Dependencies

Arch Linux: `libarchive`, `binutils`, `tar`, `zstd`, and `pacman`.

## License

GPL-2.0-or-later. Inspired by the original [debtap](https://github.com/helixarch/debtap) project by George Savvidis.

**Warning:** Review generated package metadata and maintainer scripts before installation.
