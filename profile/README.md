## Podyard

![Podyard](banner.jpg)

A pod for every tool call. Millisecond sandboxes for AI agents. Unlimited pods, every run replayable.

<p align="center">
  <a href="https://github.com/podyard/podyard">Repository</a> ·
  <a href="https://docs.podyard.dev">Docs</a> ·
  <a href="https://github.com/podyard/skills">Skills</a> ·
  <a href="https://github.com/podyard/sdk">SDKs</a> ·
  <a href="https://github.com/podyard/mcp">MCP</a> ·
  <a href="https://github.com/podyard/cli">CLI</a> ·
</p>

---

### What is Podyard?

Podyard is a hosted platform for sandboxes aimed at AI agents. Pods start in
under 5 ms on V8 isolates. When a command needs real Linux, the session moves
to a Firecracker microVM — so you only pay VM costs when you have to. Snapshot,
fork and replay any session. Network access is off by default.

Every run is on **Tape**: the ordered record of every command, output and file
change in a pod, replayable in the dashboard.

### Features

- **Millisecond starts** on V8 isolates
- **Unlimited pods** per yard
- **Snapshot, fork and replay** any session
- **Tape** — every command, output and file change is recorded and replayable
- **Network off by default**, granted per host
- **TypeScript and Python SDKs** with the same shape
- **MCP server** for use from any MCP-capable agent
- **Self-hostable** — run the platform components with `docker compose`

### Quick start

```bash
curl -fsSL https://podyard.dev/install | sh
# or: brew install podyard / npm i -g podyard

podyard login
podyard new
podyard exec my-pod -- echo "hello from a pod"
```

SDKs for TypeScript and Python expose the same shape:

```typescript
import { Podyard } from "@podyard/sdk";

const yard = new Podyard({ apiKey: process.env.PODYARD_API_KEY });
const pod = await yard.pods.create();
const result = await pod.exec("echo 'hello'");
```

### The ecosystem

| Repository | What it does |
|---|---|
| `podyard/podyard` | The hosted platform: website, docs, dashboard, HTTP API |
| `podyard/cli` | The podyard command-line interface (TypeScript, commander-based) |
| `podyard/sdk` | Official SDKs — TypeScript (`@podyard/sdk`) and Python (`podyard`) |
| `podyard/mcp` | MCP server (`@podyard/mcp`) exposing create, exec, fs and fork as tools |
| `podyard/skills` | Agent skills, `AGENTS.md` snippets, and `llms.txt` for coding agents |

### Get involved
- Browse the skills for agent-ready patterns
- Read the contributing guide and code of conduct
- Open an issue or a pull request
- Security concern? Follow SECURITY.md — do not open a public issue

<p align="center">
  Built with TypeScript · Licensed under Apache-2.0
</p>
