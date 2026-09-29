# scripts-for-waybar

A collection of small status-bar scripts for [Waybar](https://github.com/Alexays/Waybar).

## Credits

**All of these scripts belong to [Luke Smith](https://github.com/LukeSmith-dev).**
They are not my work — full credit goes to him for every script in this repository.

I have simply collected them here for convenience. If you like them, go support the
original author:

- **LARBS** — <https://github.com/LukeSmith-dev/LARBS> — his automated Linux install
  script, which bundles his full dotfiles, configs, and many more of these scripts.
- **More scripts & configs** — <https://github.com/LukeSmith-dev/scripts-for-waybar>
- **Website** — <https://lukesmith.xyz>

He doesn't post videos anymore these days, but his older content is still some of the
best Linux material out there. He is a legend in the Linux community, and I still learn
something new from everything he puts out.

## Requirements

- `sh` (any POSIX shell)
- [Waybar](https://github.com/Alexays/Waybar)
- Optional per-script dependencies — e.g. `mpv`/`playerctl`, `curl`, `wttr.in`, `curlwttr`,
  `transmission-remote`, `nmcli`, `acpi`, `xbacklight`, `brightnessctl`, `moonphase`,
  `doppler`, `btop`/`htop`, `taskwarrior`, `neomutt`, `gping`, `pacman`, etc.
  Check the top of each script for the tools it calls.

## Usage

Make a script executable and point a Waybar module at it:

```sh
chmod +x sb-clock
```

```jsonc
// ~/.config/waybar/config.jsonc
{
    "modules-right": ["custom/clock"],

    "custom/clock": {
        "format": "<icon> <text>",
        "format-icons": { "": "" },
        "on-click": "calcurse",
        "script": "~/scripts-for-waybar/sb-clock",
        "interval": 1
    }
}
```

`$BLOCK_BUTTON` is set by Waybar when a module defines an `on-click` handler, which is how
some of these scripts decide what to output.

## Scripts

| Script | Description |
| --- | --- |
| `sb-battery` | Battery percentage and status icon for all batteries |
| `sb-brightness` | Screen brightness level |
| `sb-clock` | Clock with hour, day and date indicators |
| `sb-cpu` | CPU load and frequency |
| `sb-cpubars` | Per-core CPU load as bar graphs |
| `sb-disk` | Free space for mounted disks |
| `sb-doppler` | Doppler weather radar image for a location |
| `sb-forecast` | Weather forecast from `wttr.in` |
| `sb-help-icon` | Click-to-launch help page |
| `sb-internet` | SSID, signal strength and connection state |
| `sb-iplocate` | Public IP address and location |
| `sb-kbselect` | Keyboard layout indicator |
| `sb-mailbox` | Unread mail count for configured mailboxes |
| `sb-memory` | Memory usage in GiB |
| `sb-moonphase` | Current moon phase icon |
| `sb-mpdup` | Notifies when the MPD music player daemon is playing |
| `sb-music` | Music player status: track, artist, and controls |
| `sb-nettraf` | Network traffic graph |
| `sb-news` | RSS news feed item counter |
| `sb-pacpackages` | Number of pending `pacman` upgrades |
| `sb-popupgrade` | Notifications for pending `pop upgrade` |
| `sb-price` | Stock/crypto/forex price ticker |
| `sb-tasks` | `taskwarrior` task count by urgency |
| `sb-ticker` | RSS feed headlines as a marquee |
| `sb-torrent` | `transmission-remote` torrent status |
| `sb-volume` | Audio volume and mute state |

## License

These scripts are Luke Smith's work and remain under whatever license he released them
under. See the original repository for the authoritative terms.
