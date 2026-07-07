# OpenTagger — Releases

Binary releases for [OpenTagger](https://github.com/pollomax847/opentagger), an open-source audio tagger.

This repository contains only packaged `.jar` releases and version tags — no source code.
The application itself checks this repository automatically to notify you of new versions.

## Debian/Ubuntu (apt)

A signed apt repository is published from `docs/apt/` via GitHub Pages, so `apt` resolves
dependencies (ffmpeg, bundled JRE) automatically:

```bash
curl -fsSL https://pollomax847.github.io/opentagger-releases/apt/opentagger-apt.asc \
    | sudo tee /usr/share/keyrings/opentagger.asc >/dev/null
echo "deb [signed-by=/usr/share/keyrings/opentagger.asc] https://pollomax847.github.io/opentagger-releases/apt ./" \
    | sudo tee /etc/apt/sources.list.d/opentagger.list
sudo apt update && sudo apt install opentagger
```

fpcalc (chromaprint) and SongRec are intentionally not declared as apt dependencies — fpcalc has
its own in-app installer (Preferences → Audio), and SongRec is only available from a third-party
PPA, not the official repositories.
