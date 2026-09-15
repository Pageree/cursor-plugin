# Cursor Marketplace submission

## Listing details

- **Name:** Pageree
- **Organization handle:** pageree
- **Repository:** https://github.com/Pageree/cursor-plugin
- **Website:** https://pageree.com/
- **Documentation:** https://pageree.com/docs#cursor
- **Support:** support@pageree.com
- **Logo:** `assets/logo.svg`
- **Logotype URL:** https://raw.githubusercontent.com/Pageree/cursor-plugin/main/assets/logo.svg
- **Category:** MCP / landing pages (choose the closest available category)

### Short description

Build, preview, publish, and improve landing pages with hosting, lead capture, and analytics through Pageree.

### Full description

Pageree gives Cursor the tools to take a landing page from an idea to a hosted page and improve it using real traffic data. Create a draft, review its preview, publish to a live URL, capture leads, and inspect page analytics from the same conversation.

The plugin connects to Pageree's hosted MCP server. Sign in with your Pageree account using OAuth; no local server or API key setup is required. Page-building guidance is delivered by the service alongside its tools.

Start with: "Use Pageree to create a landing page for my product. Ask me about the product and audience, then show me a draft before publishing."

## Release checks

- [x] Validate the manifest, MCP configuration, and logo path.
- [x] Publish the repository with public visibility.
- [ ] Install the plugin locally in Cursor and confirm it appears.
- [ ] Complete OAuth in Cursor with a Pageree test account.
- [ ] Call `whoami` and `list_pages` successfully through Cursor.
- [ ] Submit the repository at https://cursor.com/marketplace/publish.

Record actual results here before submission. Do not mark the Cursor checks complete based only on static configuration validation or an HTTP health check.

### Validation record — 2026-09-15

- Manifest name/version, HTTPS URLs, logo file, and exact MCP endpoint validated with Node assertions. The README JSON example matches `mcp.json`.
- SVG passes `xmllint --noout`.
- GitHub confirms the repository is public with `main` as its default branch.
- Plugin files copied to `~/.cursor/plugins/local/pageree/`. Desktop Cursor is signed out, so plugin discovery, OAuth, and tool execution remain unverified.
- Marketplace application prepared in the browser; not submitted. Submission also accepts Cursor's [Publisher Terms](https://cursor.com/marketplace-publisher-terms).

Cursor's [submission checklist](https://cursor.com/docs/reference/plugins) and [local testing guide](https://cursor.com/docs/plugins#test-plugins-locally) are the source of truth for packaging and review requirements.
