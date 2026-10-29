# ONLYOFFICE Agent Plugins

The marketplace of official ONLYOFFICE plugins for AI agents. Add it once and install any of its
plugins by name; each plugin stays updatable from the agent. It works in Claude Code, Codex and the
ChatGPT desktop app, and GitHub Copilot CLI.

## Plugins

| Plugin | What it gives the agent | Source |
|---|---|---|
| `onlyoffice-devtools` | Skills for building on the ONLYOFFICE developer SDKs: embed ONLYOFFICE Apps with the Embed SDK, build portal plugins with the Plugins SDK, build React screens with the ONLYOFFICE UI kit | [ONLYOFFICE/agent-skills](https://github.com/ONLYOFFICE/agent-skills) |

## Install

### Claude Code

```
/plugin marketplace add ONLYOFFICE/agent-plugins
/plugin install onlyoffice-devtools@onlyoffice
```

From the shell, the same is `claude plugin marketplace add ONLYOFFICE/agent-plugins` followed by
`claude plugin install onlyoffice-devtools@onlyoffice`. In the VS Code extension, type `/plugins`
in the chat, add `ONLYOFFICE/agent-plugins` on the *Marketplaces* tab, then install the plugin on
the *Plugins* tab.

`/plugin update onlyoffice-devtools@onlyoffice` installs a newer release; turning on auto-update
for the `onlyoffice` marketplace in `/plugin` does it on its own.

### Codex and the ChatGPT desktop app

```
codex plugin marketplace add ONLYOFFICE/agent-plugins
```

Then install `onlyoffice-devtools` from the `ONLYOFFICE` marketplace in the plugin list.
`codex plugin marketplace upgrade onlyoffice` fetches a newer release.

### GitHub Copilot CLI

Copilot CLI reads the same marketplace file as Claude Code:

```
copilot plugin marketplace add ONLYOFFICE/agent-plugins
copilot plugin install onlyoffice-devtools@onlyoffice
```

### Cursor and other agents

Cursor installs plugins from a marketplace repository only on its Teams and Enterprise plans, and
reads a marketplace format of its own that this repository does not carry yet. For Cursor and any
other agent, copy a plugin's skills from its repository's `plugin` branch, as the plugin's own
README describes: for `onlyoffice-devtools`, see
[Cursor and other agents](https://github.com/ONLYOFFICE/agent-skills#cursor-and-other-agents).

## How the marketplace is built

The marketplace is written twice, once per format, and both list the same plugins under the same
names:

- `.claude-plugin/marketplace.json`, read by Claude Code and GitHub Copilot CLI. Each entry repeats the plugin's name,
  description and links, because Claude Code shows an entry's own fields until the plugin is
  installed.
- `.agents/plugins/marketplace.json`, read by Codex and the ChatGPT desktop app. Each entry
  carries the `policy` and `category` Codex requires; the plugin's own `plugin.json` supplies the
  rest of its listing.

A plugin lives in its own repository and is fetched from that repository's `plugin` branch,
which the repository's release workflow builds and holds only the files the plugin ships.

To add a plugin, add an entry to both files: a `github` source in the Claude file and a `url`
source in the Codex one, each pointing at the plugin's repository and its `plugin` branch. Check
the Claude file with `claude plugin validate . --strict`.

## License

Apache-2.0. See [LICENSE](LICENSE).
