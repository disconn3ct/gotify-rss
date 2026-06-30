## Gotify-RSS

A plugin for [gotify/server](https://github.com/gotify/server) which polls RSS feed. Forked from [gotify-rss](https://github.com/solarkennedy/gotify-rss).

Written by humans. No AI has been used, and no AI is welcome in contributions, issues, etc.

## Building

For building the plugin gotify/build docker images are used to ensure compatibility with
[gotify/server](https://github.com/gotify/server).

`GOTIFY_VERSION` can be a tag, commit or branch from the gotify/server repository.

This command builds the plugin for amd64, arm-7 and arm64.
The resulting shared object will be compatible with gotify/server version 2.9.1.

```bash
$ make GOTIFY_VERSION="v2.9.1" FILE_SUFFIX="for-gotify-v2.9.1" build
```

You can also use `build-linux-amd64`, `build-linux-arm-7` or `build-linux-arm64` to build for specific architectures.

## Installation

Copy the correct library file from `build/` to the gotify plugin directory and restart gotify.

## Configuration

- `refresh_interval`: Polling interval in seconds
- `feed_urls`: URL of the RSS feed

### Example:

```yaml
refresh_interval: 1800
feed_urls:
  - https://xkcd.com/rss.xml
  - https://security.archlinux.org/advisory/feed.atom
  - https://lorem-rss.herokuapp.com/feed
```

## License

[GNU GPLv3+](LICENSE)
