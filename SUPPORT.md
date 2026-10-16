# Getting help

| I want to... | Go to |
| --- | --- |
| Set something up or learn how it works | [Documentation](https://media.kryspal.net/docs/), then [Discussions → Q&A](https://github.com/kryspal/kryspal-media/discussions/categories/q-a) |
| Report a bug | [Bug report form](https://github.com/kryspal/kryspal-media/issues/new?template=bug.yml) |
| Suggest an idea | [Discussions → Ideas](https://github.com/kryspal/kryspal-media/discussions/categories/ideas) |
| Ask about a plugin | The plugin's own repository for official plugins, or [Discussions → Plugins](https://github.com/kryspal/kryspal-media/discussions/categories/plugins) |
| Activate a license, billing or refunds | support@kryspal.net or the [contact page](https://media.kryspal.net/contact/). Never post a license code in public. |
| Report a security problem | See [SECURITY.md](SECURITY.md). Do not use public issues. |

Replies come from the maintainers and the community on a best-effort basis. We do not promise a response time and there is no service-level agreement.

## Before you post logs or screenshots

Remove license codes and email addresses, API keys and tokens, your public domain or IP address, signed playback URLs, and any media titles or file paths you consider private (write `Movie A` or `/media/...` instead). The admin console masks keys and signatures when it writes the log, but please read it again before you paste.

## What a good bug report has

The [bug report form](https://github.com/kryspal/kryspal-media/issues/new?template=bug.yml) asks for these on purpose; reports without them are hard to act on.

- **One problem per issue**, with what you did, what you expected and what happened instead.
- **Server version** and whether it is the latest release. Please try the latest release first.
- **Steps that reproduce it**, and whether it happens every time or only sometimes.
- **Your setup:** install method, NAS or system and CPU architecture, the client and its version, and whether the server is in Emby or Jellyfin compatibility mode.
- **A log excerpt** from System → System log (Export): only the lines around the problem, with private details removed.
- **For playback problems,** the player, whether it was direct play or a repackaged stream, and the container and codecs of the file (not its name).

## What happens next

A maintainer reads new issues, adds labels, and asks for missing details. An issue that is missing details may wait until you add them, and may be closed if it stays unanswered. Issues we can reproduce are passed to the people who own that part of the product; we cannot say when a fix will ship.

Duplicates are closed with a link to the original: add what is new there. Questions and ideas are moved to Discussions.
