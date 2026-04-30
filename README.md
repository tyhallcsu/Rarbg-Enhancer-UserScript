<div align="center">
  <img src="./assets/readme-icon.svg" alt="RARBG Enhancer UserScript icon" width="142">

  <h1>RARBG Enhancer UserScript</h1>

  <p><strong>A userscript fork that adds CAPTCHA handling, infinite scroll, thumbnails, mirror switching, magnet shortcuts, and UI controls for RARBG-style mirror pages.</strong></p>

  <p>
    <a href="./LICENSE"><img src="https://img.shields.io/github/license/tyhallcsu/Rarbg-Enhancer-UserScript" alt="License"></a>
    <img src="https://img.shields.io/badge/type-userscript-31b37d" alt="Type: userscript">
    <img src="https://img.shields.io/badge/version-6.0.1-5965f2" alt="Version 6.0.1">
  </p>

  <p>
    <a href="#install">Install</a> &middot;
    <a href="#features">Features</a> &middot;
    <a href="#screenshots">Screenshots</a> &middot;
    <a href="#keyboard-shortcuts">Keyboard shortcuts</a> &middot;
    <a href="#license">License</a>
  </p>
</div>

## Overview

RARBG Enhancer UserScript is a browser userscript for RARBG-style mirror pages. The main script adds table enhancements, thumbnail handling, magnet and torrent shortcuts, mirror navigation, configurable options, and keyboard shortcuts on pages matched by the userscript metadata.

The repository also includes a smaller CAPTCHA-focused userscript for users who only want the CAPTCHA helper behavior. The official RARBG site is no longer online, but the userscript metadata still targets RARBG-style mirrors and related domains.

## Status

| Area | Current state |
|---|---|
| Main script | [`Rarbg-Enhancer-UserScript.user.js`](./Rarbg-Enhancer-UserScript.user.js), version `6.0.1` |
| CAPTCHA-only script | [`Rarbg-CAPTCHA-solver.user.js`](./Rarbg-CAPTCHA-solver.user.js), version `1.1` |
| Userscript manager | Tampermonkey-compatible APIs are used (`GM_*`, `unsafeWindow`, `GM_config`) |
| Documentation | [`docs.md`](./docs.md) contains implementation notes |
| License | MIT, from [`LICENSE`](./LICENSE) |
| CI/tests | Not configured in this repo |

## Install

Install a userscript manager first. The original project notes Tampermonkey as the tested option, and the scripts use userscript-manager APIs such as `GM_setValue`, `GM_getValue`, `GM_download`, `GM_xmlhttpRequest`, and `GM_registerMenuCommand`.

Then install one script:

| Script | Use it when | Install |
|---|---|---|
| [`Rarbg-Enhancer-UserScript.user.js`](./Rarbg-Enhancer-UserScript.user.js) | You want the full UI enhancement script. | [Open raw script](https://github.com/tyhallcsu/Rarbg-Enhancer-UserScript/raw/master/Rarbg-Enhancer-UserScript.user.js) |
| [`Rarbg-CAPTCHA-solver.user.js`](./Rarbg-CAPTCHA-solver.user.js) | You only want the standalone CAPTCHA helper. | [Open raw script](https://github.com/tyhallcsu/Rarbg-Enhancer-UserScript/raw/master/Rarbg-CAPTCHA-solver.user.js) |

Your userscript manager should prompt you to review and install the selected file after opening the raw script link.

## Features

- **CAPTCHA helper.** Attempts to solve CAPTCHA and browser-verification page behavior declared in the userscript.
- **Infinite scrolling.** Appends the next results page when the site exposes a next-page link and the option is enabled.
- **Torrent thumbnails.** Adds thumbnail cells to torrent rows and supports small/large thumbnail toggling.
- **Image search shortcuts.** Adds search links for description thumbnails and extra images through configured search engines.
- **Magnet and torrent shortcuts.** Adds magnet and torrent download controls to results rows.
- **Mirror switcher.** Adds a mirror dropdown from the configured mirror list.
- **Download-all action.** Adds a table-header action that prompts before opening visible torrent links.
- **Options menu.** Registers a userscript menu command and `ctrl+/` shortcut for the settings panel.

## Screenshots

<p align="center">
  <img src="./screenshots/Screenshot_Rarbg_general.png" alt="RARBG page enhanced by the userscript" width="85%">
</p>

<details>
<summary>Feature demos</summary>

### CAPTCHA helper

<p align="center">
  <img src="./screenshots/Screenshot_auto-captcha.gif" alt="Automatic CAPTCHA helper demo" width="85%">
</p>

### Infinite scrolling

<p align="center">
  <img src="./screenshots/infinit-scroll.gif" alt="Infinite scrolling demo" width="85%">
</p>

### Thumbnails

<p align="center">
  <img src="./screenshots/Screenshot_thumbnails-before-after.gif" alt="Thumbnail before and after demo" width="85%">
</p>

### Extra thumbnails

<p align="center">
  <img src="./screenshots/extra_thumbnails.gif" alt="Extra thumbnails demo" width="85%">
</p>

### Mirror dropdown

<p align="center">
  <img src="./screenshots/Screenshot_Rarbg_mirrorDropdown.png" alt="Mirror dropdown screenshot" width="70%">
</p>

### Download all

<p align="center">
  <img src="./screenshots/Screenshot_Rarbg_download_all_torrents.png" alt="Download all torrents screenshot" width="85%">
</p>

### Options

<p align="center">
  <img src="./screenshots/options_button.png" alt="Options button screenshot" width="75%">
  <br><br>
  <img src="./screenshots/rarbg-options-page.png" alt="Options page screenshot" width="75%">
</p>

</details>

## Keyboard shortcuts

| Shortcut | Action |
|---|---|
| `/` | Focus and select the site search input. |
| `ctrl+/` | Open the userscript options panel. |
| `` ` `` | Toggle thumbnail size. |
| `ctrl+s` | Save an HTML/JSON summary of visible torrent rows. |
| `d a` | Fetch description images for rows with description-image controls. |
| `=` | Increase thumbnail size. |
| `-` | Decrease thumbnail size. |

## Project structure

```text
.
|-- Rarbg-Enhancer-UserScript.user.js
|-- Rarbg-CAPTCHA-solver.user.js
|-- docs.md
|-- icons/
|-- screenshots/
|-- LICENSE
`-- README.md
```

## Safety and legality

This project modifies the browser UI for pages that match its userscript metadata. Review the script before installing it, keep your userscript manager up to date, and only use it in ways that comply with the laws and site rules that apply to you. This repository documents UI automation behavior; it does not endorse piracy.

## Credits

This fork preserves upstream credit in the userscript metadata:

- **Faris Hijazi** for the original RARBG Enhancer userscript.
- **darkred** for code referenced from Greasy Fork magnet/torrent-link and timestamp scripts.
- **Cisco** for the earlier RARBG magnet-link script that inspired the original project.

## License

This project is licensed under the [MIT License](./LICENSE).
