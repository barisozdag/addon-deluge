# barisozdag's Personal Home Assistant Add-ons: Deluge

Lightweight, Free Software, cross-platform BitTorrent client.

## Installation

The installation of this add-on is pretty straightforward and not different in
comparison to installing any other Home Assistant add-on.

1. [Add my Hass.io add-ons repository][repository] to your Hass.io instance.
1. Search for the “Deluge” add-on and install it.
1. Save the add-on configuration.
1. Start the "Deluge" add-on.
1. Check the logs of the "Deluge" to see if everything went well.
1. Login to the web interface.

## Web-UI

Web-UI can be found at `<your-ip>:8112`.

## Configuration

**Note**: _Remember to restart the add-on when the configuration is changed._

Example add-on configuration:

```yaml
DELUGE_LOGLEVEL: info
```

**Note**: _This is just an example, don't copy and paste it! Create your own!_

### Option: `DELUGE_LOGLEVEL`

The `DELUGE_LOGLEVEL` option controls the level of log output by the addon and
can be changed to be more or less verbose, which might be useful when you are
dealing with an unknown issue. Possible values are: `none`, `critical`,
`error`, `warning`, `info`, `debug`.

**Note**: _`debug` is very verbose and with a lot of torrents log files will be
MB's in size._

## Changelog & Releases

This repository keeps a change log using [GitHub's releases][releases]
functionality.

Releases are based on [Semantic Versioning][semver], and use the format
of `MAJOR.MINOR.PATCH`. In a nutshell, the version will be incremented
based on the following:

- `MAJOR`: Incompatible or major changes.
- `MINOR`: Backwards-compatible new features and enhancements.
- `PATCH`: Backwards-compatible bugfixes and package updates.

## Support

Got questions?

You could [open an issue here][issue] GitHub.

## Authors & contributors

The original setup of this repository is by [Barış Özdağ][barisozdag].

For a full list of all authors and contributors,
check [the contributor's page][contributors].

## License

MIT License

Copyright (c) 2021 Barış Özdağ

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[contributors]: https://github.com/barisozdag/addon-deluge/graphs/contributors
[barisozdag]: https://github.com/barisozdag
[issue]: https://github.com/barisozdag/addon-deluge/issues
[releases]: https://github.com/barisozdag/addon-deluge/releases
[repository]: https://github.com/barisozdag/haddons-repo
[semver]: http://semver.org/spec/v2.0.0.htm
