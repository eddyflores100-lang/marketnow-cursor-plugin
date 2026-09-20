# MarketNow — Trust Layer for AI Agents (Cursor Plugin)

**Every MCP tool call is remote code execution with your credentials. MarketNow is the pre-call trust gate.**

This Cursor plugin bundles the [MarketNow MCP server](https://www.marketnow.site) — a free trust layer for AI agents on the Model Context Protocol. No API key required: the public tools work out of the box, and the remote endpoint means zero install, zero local dependencies.

## What your agent gets

| Tool group | What it does |
|---|---|
| **ATC verify** | Verify any Agent Trust Card (ATC/1.0): issuer signature, evidence chain, revocation status — against the published spec, no hallucinations |
| **Domain scam-check** | WHOIS domain age (live RDAP), TLS certificate inspection (issuer, expiry, SAN match), scam scoring with transparent per-check reasons |
| **Tool fingerprinting** | Hash tool definitions and compare against the OWASP MCP Top-10 tool-poisoning indicators (TFP-1.0 fingerprints) |
| **Registry search** | Search 68,000+ indexed MCP servers with trust metadata — find safe alternatives to an untrusted tool |
| **12-stage pipeline** | The full verification pipeline (credential formats, behavior, policy, trajectory) powers every score |

## Why trust verification matters

AI coding agents now connect to dozens of third-party MCP servers they have never met. A poisoned tool definition, a lookalike domain, or a revoked credential is enough to exfiltrate a source tree. MarketNow gives the agent a cheap pre-call check — the same instinct a senior engineer has before `curl | bash`.

## Install

Install from the Cursor Marketplace (search **MarketNow**), or add manually to your `mcp.json`:

```json
{
  "mcpServers": {
    "marketnow": {
      "type": "http",
      "url": "https://www.marketnow.site/api/mcp"
    }
  }
}
```

No environment variables needed — public tools are free and keyless.

## Links

- Website: https://www.marketnow.site
- MCP server repo: https://github.com/alicelabs-llc/universal-trust-adapter
- npm: [`marketnow-mcp`](https://www.npmjs.com/package/marketnow-mcp) · [`agent-trust-card`](https://www.npmjs.com/package/agent-trust-card) · `@marketnow/*` (14 packages)
- Security contact: info@alicelabs.site

## License

Dual-licensed under **MIT OR Apache-2.0, at your option** — free for any use, including commercial use. This plugin and all MarketNow npm packages ship dual-licensed: see [LICENSE-MIT](LICENSE-MIT) and [LICENSE-APACHE](LICENSE-APACHE). Trademarks ("MarketNow", "UTA", "ATC") are reserved by AliceLabs LLC — see [NOTICE](NOTICE).
