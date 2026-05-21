<<<<<<< HEAD
# 🔗 AfterLink — Agent Skill

> AI agent skill for building real-time Node.js apps with AfterLink — a 10-byte binary protocol that's 76% faster than WebSocket.

[![npx skills add](https://img.shields.io/badge/npx_skills_add-AJAYMYTH%2Fafterlink--skill-blue)](https://skills.sh)
[![Supports 40+ agents](https://img.shields.io/badge/supports-40%2B_agents-green)](https://skills.sh)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## What This Skill Does

- Gives AI agents (Claude, Cursor, Copilot, Windsurf, etc.) full knowledge of AfterLink's API, patterns, and best practices
- Provides copy-paste ready code for pub/sub, streaming, middleware, TLS, browser bridges, testing, and more
- Installs in one command — no manual setup required

## Install

```bash
# Method 1: skills CLI (recommended)
npx skills add AJAYMYTH/afterlink-skill

# Method 2: agent-skills-cli (cross-agent)
npx agent-skills-cli@latest add AJAYMYTH/afterlink-skill

# Method 3: Claude Code plugin
claude plugin install https://github.com/AJAYMYTH/afterlink-skill
```

## Supported Agents

| Agent | Install Method |
|-------|---------------|
| Claude Code | `npx skills add` or plugin |
| Cursor | `npx skills add` |
| GitHub Copilot | `npx skills add` |
| Windsurf | `npx skills add` |
| OpenCode | `npx skills add` |
| 40+ more | `npx agent-skills-cli@latest add` |

## What the Skill Covers

1. Scaffolding a new AfterLink server + client
2. Pub/Sub messaging patterns
3. Streaming data with STREAM frames
4. Middleware (JWT auth + logging)
5. TLS setup (dev certs + production)
6. Browser WebSocket bridge
7. Health endpoint configuration
8. Rate limiting + compression
9. Integrating AfterLink into existing projects
10. Writing tests for AfterLink routes

## Quick Example

```js
const { Server } = require('@afterlink/server');
const { Client } = require('@afterlink/client');

// Server
const server = new Server({ port: 4000 });
server.on('ping', async (req, res) => {
  res.send({ message: 'pong', ts: Date.now() });
});
server.listen();

// Client
const client = new Client('afterlink://localhost:4000');
await client.connect();
const result = await client.request('ping', {});
console.log(result); // { message: 'pong', ts: 1716300000000 }
```

## About AfterLink

AfterLink is a custom binary protocol for Node.js built by [Javali Ajayakumar (AJAYMYTH)](https://github.com/AJAYMYTH). It achieves 30,167 msg/sec with 0.033ms avg latency — 76% faster than WebSocket.

- **npm:** https://www.npmjs.com/package/afterlink
- **GitHub:** https://github.com/AJAYMYTH/AfterLink
- **Docs:** https://afterlinkdocs.vercel.app

## License

MIT — see [LICENSE](./LICENSE) for details.
