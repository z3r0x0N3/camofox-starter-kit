# Camofox Starter Kit

**Stealth browsing for agent stacks, wired in an afternoon.** This kit packages the MIT-licensed [Camofox](https://github.com/camofox-browser/camofox) stealth browser toolkit with battle-tested MCP integration recipes — the exact wiring we run in production for autonomous browsing, form-filling, and snapshot-driven extraction.

Available as a [**Starter Kit on Gumroad**](https://ipoole.gumroad.com/l/cbuehb?utm_source=github&utm_medium=repo&utm_campaign=launch) ($29).

## Why Camofox

Chrome-driven automation gets fingerprinted, captcha'd, and 403'd. Camoufox (Firefox-based, stealth-hardened) passes where headless Chrome fails:

- Realistic fingerprints that survive bot-detection surfaces
- Snapshot-first interaction model (aria snapshots with element refs — an LLM can read the page and act)
- REST + MCP server included: `create_tab` → `snapshot` → `type`/`click` → verify

## What the kit adds

| File | What you get |
|---|---|
| `QUICKSTART.md` | From zero to first automated browsing session |
| `mcp-integration-recipes.md` | Three production wiring patterns: stdio MCP wrapper, REST direct, session-persistent agent |
| `ATTRIBUTION.md` | Clean MIT compliance for the upstream project |

## Recipe A in 30 seconds

```js
import { spawn } from "node:child_process";
import readline from "node:readline";

const browser = spawn("./run.sh", ["--headless"], { stdio: ["pipe", "pipe", "pipe"] });
// JSON-RPC over stdio: tools/list, browse, snapshot, extract
```

Full working MCP server (~120 lines, running in production today) is in the kit.

## Who this is for

- Agent authors who need browsing that doesn't get blocked on first contact
- Teams building scraping/monitoring with session persistence
- Anyone wiring an LLM to a browser and tired of maintaining the plumbing

Upstream is [Camofox](https://github.com/camofox-browser/camofox) (MIT) — this kit is packaging + recipes; upstream files included unmodified with attribution. [Get the kit](https://ipoole.gumroad.com/l/cbuehb?utm_source=github&utm_medium=repo&utm_campaign=launch).
