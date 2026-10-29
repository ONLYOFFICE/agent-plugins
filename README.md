# ONLYOFFICE Agent Plugins

The marketplace of official ONLYOFFICE plugins for AI agents. Add it once and install any of its
plugins by name; each plugin stays updatable from the agent.

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

## How the marketplace is built

`.claude-plugin/marketplace.json` lists each plugin and where to fetch it. A plugin lives in its
own repository and is fetched from that repository's `plugin` branch, which the repository's
release workflow builds and holds only the files the plugin ships. Each entry repeats the
plugin's name, description and links, because the agent shows an entry's own fields until the
plugin is installed.

To add a plugin, add an entry with a `github` source pointing at its repository and branch, and
check the file with `claude plugin validate . --strict`.

## License

Apache-2.0. See [LICENSE](LICENSE).
