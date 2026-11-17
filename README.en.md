<div align="center">

<img src="https://raw.githubusercontent.com/mainuan/.github/main/profile/assets/mainuan-logo.svg" width="96" alt="Mainuan logo">

# Mainuan Wallpapers

Wallpapers of **Mainuan Linux** for KDE Plasma, packaged as `mainuan-wallpapers`.

[![CI](https://github.com/mainuan/wallpapers/actions/workflows/ci.yml/badge.svg)](https://github.com/mainuan/wallpapers/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/v/release/mainuan/wallpapers)](https://github.com/mainuan/wallpapers/releases)
[![License](https://img.shields.io/github/license/mainuan/wallpapers)](LICENSE)

[Português](README.md)

</div>

---

## What it is

The `mainuan-wallpapers` Debian package installs the 27 images at the root of
this repository into `/usr/share/wallpapers`, where Plasma lists them in
**Configure Desktop and Wallpaper**. It ships with the Mainuan ISO. The default
wallpaper (`01ciano.png`) is set by
[`mainuan-desktop-defaults`](https://github.com/mainuan/dot-files), not here.

Contents: the six Mainuan accent colours (`01ciano` … `06lima`, PNG,
1920×1080), three hummingbird images, eight illustrations, three photos and
seven JPEG XL images (opened by Plasma through `kimageformat6-plugins`, which
the package recommends).

The package only adds new files. It neither replaces nor diverts any file of
`breeze-wallpaper`, `kubuntu-wallpapers` or `plasma-workspace-wallpapers`.

## Installation

Download the `.deb` and `SHA256SUMS` from the
[latest release](https://github.com/mainuan/wallpapers/releases/latest):

```bash
sha256sum --check --ignore-missing SHA256SUMS
sudo apt install ./mainuan-wallpapers_*_all.deb
```

## Build and tests

```bash
dpkg-buildpackage -us -uc -b
```

The [CI](.github/workflows/ci.yml) builds the package in Ubuntu 26.04, runs
`lintian`, installs it next to Kubuntu's wallpapers, checks every image type
and the 1920×1080 accent images, verifies that Kubuntu's packages are
untouched, then reinstalls, removes and purges it. A `v<version>` tag
publishes the `.deb` and `SHA256SUMS`.

To add a wallpaper: put the image at the repository root (PNG, JPEG or
JPEG XL), update the expected count in the CI smoke test and add a
`debian/changelog` entry.

## Credits and license

Wallpapers by Daigo ([daigoasuka](https://github.com/daigoasuka)); Debian
packaging and CI by Rafael Ruscher ([ruscher](https://github.com/ruscher)).
Licensed under the [GNU GPL version 3](LICENSE), which `debian/copyright`
applies to all images.
