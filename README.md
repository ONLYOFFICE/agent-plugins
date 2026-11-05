# ONLYOFFICE Agent Plugins

The marketplace of official ONLYOFFICE plugins for AI agents. Add it once, then install any of
its plugins by name and update them from your agent.

The marketplace is described twice, once per format, and both files list the same plugins under
the same names:

| Location | Format reference |
|---|---|
| `.claude-plugin/marketplace.json` | [Claude Code plugin marketplaces] |
| `.agents/plugins/marketplace.json` | [Codex plugin marketplace] |

## Plugins

| Plugin | What it gives the agent | Source |
|---|---|---|
| `onlyoffice-devtools` | Skills for building on the ONLYOFFICE developer SDKs: embed ONLYOFFICE Apps with the Embed SDK, build portal plugins with the Plugins SDK, build React screens with the ONLYOFFICE UI kit | [ONLYOFFICE/agent-skills](https://github.com/ONLYOFFICE/agent-skills) |
| `onlyoffice-apps` | The hosted ONLYOFFICE Apps MCP server: manage rooms, folders, files and people on your portal | [ONLYOFFICE/docspace-mcp](https://github.com/ONLYOFFICE/docspace-mcp/tree/main/plugin) |

Each plugin's README, linked under *Source*, describes what the plugin needs and how to use it in
agents that read neither format.

## Install

Add the marketplace and install a plugin from the table above with your agent's plugin command:

```bash
<your-agent> plugin marketplace add ONLYOFFICE/agent-plugins
<your-agent> plugin install <plugin>@onlyoffice
```

If your agent has no install command, pick the plugin from the `onlyoffice` marketplace in its
plugin list instead. Updating the marketplace from the agent brings in newer plugin releases.

### Popular agents

These agents can add this marketplace; their documentation shows how to add a marketplace and
install, update and remove its plugins:

- [Claude Code](https://code.claude.com/docs/en/discover-plugins)
- [ChatGPT and Codex](https://developers.openai.com/codex/plugins) (to add a marketplace, see
  [`codex plugin marketplace add`](https://developers.openai.com/codex/plugins/build))
- [GitHub Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/plugins-finding-installing)

## License

Apache-2.0. See [LICENSE](LICENSE).

<!-- Footnotes -->

[Claude Code plugin marketplaces]: https://code.claude.com/docs/en/plugin-marketplaces
[Codex plugin marketplace]: https://developers.openai.com/codex/plugins/build
