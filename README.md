<div align="center"><p align="center"><img src="https://gnos.in/img/shot/common/gnos-browser-selector_0.png"></img></p></div>

# GNOS Browser Selector

GUI to select your browser on demand

- Configurable browser list
- One-click browser selection/discard
- Calling app detection with icon
- Remember user choice by calling app and/or domain
- Great in conjunction with [gnos-browser-factory](https://github.com/gnos-project/gnos-browser-factory) profiles

## Use

```
browse [-app CALLING_APP_NAME] [URL]
```

## Configure

### Installed browsers

To include a browser simply symlink its `.desktop` to launcher to `~/.config/browser/`.

### Prefered browsers

User selections are stored in `~/.config/browser/config.csv` file, columns are:

- `LAUNCHER_NAME` is the installed browser launcher file name, without '.desktop' extension
- `CALLING_APP` is the calling binary name, empty means any
- `DOMAIN` is the destination domain name, empty means any

## Install

Depends on [`sugar`](https://github.com/gnos-project/gnos-sugar), `yad` & `crudini`.

GNOS [installer](https://github.com/gnos-project/gnos-gnowlegde) automatically  hijacks browser launching mecanisms, for manual installation you should check:

- `$BROWSER` environment variable
- `update-alternatives` for registering `x-www-browser` & `gnome-www-browse`
- `xdg-settings` for setting default browser
- `xdg-mime` for registering various `x-scheme-handler/*`
- KDE kdeglobals `BrowserApplication` attribute
- you may also symlink to `/usr{,/local}/bin` for silly apps
