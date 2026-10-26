# caelestia-plus packages

The pacman repo for [caelestia-plus](https://github.com/moimart/caelestia-plus),
a Caelestia-based Hyprland desktop. CI builds and signs the packages and
publishes them to GitHub Pages:
https://moimart.github.io/caelestia-plus-packages/

## Use it

Trust the signing key once:

```sh
curl -sL https://moimart.github.io/caelestia-plus-packages/caelestia-plus.asc | sudo pacman-key --add -
sudo pacman-key --lsign-key BC40964C5AA4206E09F6148BD849D193EECADBBB
```

Add the repo to `/etc/pacman.conf`:

```ini
[caelestia-plus]
SigLevel = Required
Server = https://moimart.github.io/caelestia-plus-packages/$arch
```

Then install the desktop and set up your user:

```sh
sudo pacman -Syu caelestia-plus
caelestia-plus-setup
```

Signing key: `BC40964C5AA4206E09F6148BD849D193EECADBBB` (`caelestia-plus.asc` here).

The packages: `caelestia-plus` (everything), `caelestia-shell-moimart`,
`caelestia-plus-hypr`, `caelestia-plus-config`, and the AUR packages they need
(`quickshell-git`, `caelestia-cli`, `app2unit`, `libcava`), built here so they always match.
