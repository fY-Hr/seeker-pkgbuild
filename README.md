# seeker PKGBUILD

Arch Linux package recipe for `seeker`.

## Prerequisites

Install base packaging tools:

```bash
sudo pacman -S --needed base-devel git
```

Install dependencies used by this PKGBUILD:

```bash
sudo pacman -S --needed \
  gtk3 webkit2gtk-4.1 libappindicator-gtk3 librsvg \
  npm bun rust cargo
```

## Build and install

From this directory (`seeker-pkgbuild`):

```bash
makepkg -si
```

This will:
- download the source tarball for the version set in `PKGBUILD`
- build `seeker`
- install the package with `pacman`

## Rebuild after PKGBUILD changes

```bash
makepkg -Csi
```

Use `-C` to clean previous build artifacts before rebuilding.

## Uninstall

```bash
sudo pacman -R seeker
```
