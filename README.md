# Pageree for Cursor

<img src="assets/logo.svg" alt="Pageree" width="64" height="64">

Build and run landing pages from Cursor. Pageree connects your agent to hosted previews, publishing, lead capture, and page analytics through a remote MCP server.

This repository contains the Cursor plugin configuration. Pageree hosts the service; there is no local server or dependency installation.

## Requirements

- A current version of Cursor with plugin support.
- A [Pageree account](https://console.pageree.com/signup).
- Internet access to `https://mcp.pageree.com/`.

Service usage is subject to your [Pageree plan](https://pageree.com/#pricing).

## Install the plugin locally

Marketplace publication is pending. You can install this package locally now:

```sh
git clone https://github.com/Pageree/cursor-plugin.git
mkdir -p "$HOME/.cursor/plugins/local"
cp -R cursor-plugin "$HOME/.cursor/plugins/local/pageree"
```

Use an unused destination for the first install. To update an existing local installation, replace its plugin files with the latest version. Copy the directory instead of symlinking it: Cursor skips symlinks that point outside its local plugin directory.

1. Restart Cursor or run **Developer: Reload Window** from the Command Palette.
2. Open **Customize** and confirm the Pageree plugin and its MCP server appear.
3. Connect the Pageree server, then sign in and authorize it in your browser when prompted.
4. Return to Cursor and confirm its tools are available.

Your team may need to allow local plugin imports. See [Cursor's local testing instructions](https://cursor.com/docs/plugins#test-plugins-locally).

### Alternative: connect MCP directly

If local plugins are unavailable, merge this entry into `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one project), preserving your existing servers:

```json
{
  "mcpServers": {
    "pageree": {
      "url": "https://mcp.pageree.com/"
    }
  }
}
```

Connect and authorize Pageree in Cursor's MCP settings. Use either the plugin or the direct configuration to avoid duplicate tools. The server URL ends at `/`; do not append `/mcp` or `/sse`. Authentication uses OAuth, so you do not need to paste an API key into this file.

## Verify the connection

In a new Agent chat, ask:

> Use Pageree to call whoami and list_pages. Do not create, change, or publish anything.

You should see your connected account and its pages. An empty page list is expected for a new account.

## Try it

**Create a preview**

> Use Pageree to create a landing page for my product. First ask me about the product, audience, and desired action. Save a draft and show me the preview before publishing.

**Publish an approved draft**

> Publish the Pageree draft I just approved to the subdomain we chose.

**Improve an existing page**

> Use Pageree to review my page's analytics. Explain what the data supports and propose changes. Wait for my approval before editing or publishing.

Pageree provides its page-building guidance through MCP tools. The plugin does not need additional rules or skills to keep that guidance current. Publishing makes a page public; review your draft and confirm the destination first.

## Troubleshooting

| Symptom | What to check |
| --- | --- |
| Plugin is missing | Confirm `.cursor-plugin/plugin.json` is inside `~/.cursor/plugins/local/pageree/`, reload Cursor, and check whether your team permits local imports. |
| Server needs authentication | Connect or reconnect Pageree in MCP settings and finish the browser authorization flow. |
| No tools appear | Confirm the server is enabled, use the exact root URL above, and start a new Agent chat after connecting. |
| Duplicate tools | Remove the duplicate manual MCP entry if you installed the plugin. |
| Wrong account | Disconnect and reconnect, signing in to the intended Pageree account. |

## Package contents

```text
.cursor-plugin/plugin.json   Plugin metadata
mcp.json                    Hosted MCP connection
assets/logo.svg             Pageree logo
```

The package has no executable hooks, bundled server, or credentials. Cursor stores authentication state separately. Requests made with Pageree tools go to the hosted Pageree service.

## Links

- [Setup documentation](https://pageree.com/docs#cursor)
- [Pageree dashboard](https://console.pageree.com/)
- [Privacy policy](https://pageree.com/privacy) · [Terms](https://pageree.com/terms)
- [Cursor plugin specification](https://cursor.com/docs/reference/plugins)
- Support: [support@pageree.com](mailto:support@pageree.com)
