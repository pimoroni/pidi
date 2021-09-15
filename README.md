# 🎵 pidi

[![PyPI](https://img.shields.io/pypi/v/pidi.svg)](https://pypi.python.org/pypi/pidi/)
[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE.md)
![GitHub Workflow Status](https://img.shields.io/github/workflow/status/pimoroni/pidi/CMake)
[![Donate](https://img.shields.io/badge/donate-patreon-yellow.svg)](https://www.patreon.com/dyla)

`pidi` is a plugin-compatible fork of `bum`, a daemon that downloads album art for songs playing in `mpd`/`mopidy` and displays them in a little window. 

`pidi` isn't as lightweight as `bum`, but supports displaying track information to a variety of output devices including a 240x240 ST7789 LCD. `pidi` is intended for use with the Raspberry Pi, but can be used on other systems with the appropriate display plugins.

`pidi` uses [musicbrainz](https://musicbrainz.org/) to source and download cover art, if an album is missing its cover art you can easily create an account and fill in the data yourself. `pidi` outputs a `release-id` which you can use to find the exact entry on musicbrainz.

Note: `pidi` is meant to be used with files that don't have embedded album art (eg: `mopidy-spotify`).


![showcase](http://i.imgur.com/uKomDoL.gif)


## Dependencies

- `python 3.6+`
- `python-mpd2`
- `musicbrainzngs`

### Optional

`pidi` supports multiple display outputs, specified using `--display {dummy,tk,mpv}`, you must install the dependencies required for your chosen output:

- `python-mpv` - for mpv output
- `python3-pil`, `python3-tk` and `python3-pil.imagetk` plus `fonts` and `font_connection` from pypi - for tk/PIL output
- `st7789` - for ST7789 1.3" 240x240 LCD output

## Installation

```sh
pip3 install --user pidi
```

## Usage

```sh
usage: pidi [-h] [--update-interval "i"] [--fps FPS] [--size "px"] [--cache_dir "/path/to/dir"] [--version]
            [--no_display] [--display {dummy,mpv,file,tk}] [--client {mpd,ssnc}] [--port PORT]
            [--server SERVER]

pidi - Download and display album art for mpd tracks.

optional arguments:
  -h, --help            show this help message and exit
  --update-interval "i"
                        overlay update interval in seconds.
  --fps FPS             frames per second.
  --size "px"           what size to display the album art in.
  --cache_dir "/path/to/dir"
                        Where to store the downloaded cover art.
  --version             Print "pidi" version.
  --no_display          Only download album art, don't display.
  --display {dummy,mpv,file,tk}
                        Display class to use.
  --client {mpd,ssnc}   Client class to use.
  --port PORT           Use a custom mpd port.
  --server SERVER       Use a remote server instead of localhost.
```

## Changelog

### v0.1.0

* Add ability to plug clients into pidi
* Add Shairport Sync client - see https://github.com/pimoroni/pidi/issues/5
* Fix compatbility with new versions of mpv and python-mpd2

### v0.0.1 / 0.0.2

* Initial release(s)

## Donate

`pidi` is a fork of `bum` - https://github.com/dylanaraps/bum, which was originally written by @dylanaraps.

If you'd like to show him some support, you can donate here:

**https://patreon.com/dyla**
