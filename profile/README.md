<p align="center">
  <a href="https://tracksidehq.dev">
    <img src="https://tracksidehq.dev/icon.svg" width="112" alt="Trackside icon: the letter T drawn as a track junction">
  </a>
</p>

<h1 align="center">Trackside</h1>

<p align="center">
  <b>Run AI agents side by side, under your rules.</b><br>
  A desktop workbench for AI coding agents: compare them on the same task, decide what each one may do, and keep a record of every tool call it judges.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/status-demo%200.1.0-111111?style=flat-square&labelColor=000000" alt="Status: demo 0.1.0">
  <img src="https://img.shields.io/badge/platform-macOS%20first-111111?style=flat-square&labelColor=000000&logo=apple&logoColor=white" alt="Platform: macOS first">
  <br>
  <img src="https://img.shields.io/badge/Rust-111111?style=flat-square&logo=rust&logoColor=white" alt="Rust">
  <img src="https://img.shields.io/badge/Tauri%202-111111?style=flat-square&logo=tauri&logoColor=white" alt="Tauri 2">
  <img src="https://img.shields.io/badge/TypeScript-111111?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/SolidJS-111111?style=flat-square&logo=solid&logoColor=white" alt="SolidJS">
  <img src="https://img.shields.io/badge/Vite-111111?style=flat-square&logo=vite&logoColor=white" alt="Vite">
  <img src="https://img.shields.io/badge/MCP-111111?style=flat-square&logo=modelcontextprotocol&logoColor=white" alt="Model Context Protocol">
</p>

<p align="center">
  <a href="https://tracksidehq.dev"><b>Website</b></a>
</p>

<p align="center">
  <a href="https://tracksidehq.dev">
    <img src="https://tracksidehq.dev/og.png" width="820" alt="The Trackside website: Run AI agents side by side, under your rules">
  </a>
</p>

---

## What it is

Coding agents are good enough to be handed real work, and they run with your shell, your files and your credentials. Trackside is the place where you watch them do it.

- **Compare.** Real terminals in tabs and split panes, one agent in each. Send the same prompt to every pane and read the answers next to each other: Claude Code, Codex, and local models through Ollama.
- **Govern.** One policy file, written by you, says what each agent may do. An MCP gateway sits in front of the tools (allow, ask, deny) and an agent hook covers the shell and the file tools, by tool name and by file path. A denied call does not reach the tool.
- **Audit.** Every decision goes to a hash-chained trail before it takes effect. You can verify the chain and export it.

It runs on your machine. Your code and your prompts do not pass through us, and there is no telemetry. The demo asks you to sign in once with a demo account, and then works offline until that access expires.

## Why the name

Trackside is where a race team stands: every car in view at once, telemetry on the screen, and the call to make when something goes wrong. That is the job here, with agents instead of cars. The icon is the letter T drawn as a track junction, in the lines of a technical drawing.

## How it started

Trackside began in November 2026 as a personal project, around one question: can several coding agents be put on the same task, side by side, with one set of rules and one record of what happened?

It is built in small slices. Each one ships with its tests, its documentation and a written decision record that says what was chosen, what was left out and what was not tested.

## Where it stands

In active development, macOS first. Working today in the demo:

| Area | State |
|---|---|
| Terminals in tabs and split panes, sessions that survive closing the window | working |
| Same prompt to every pane | working |
| Usage and cost read from the agent's own records | working |
| Local models through Ollama | working |
| MCP gateway: allow, ask, deny per tool; denied tools hidden from the agent; tool definitions pinned by hash | working, for stdio servers of an agent Trackside launches |
| Agent hook for shell and file tools, by tool and by path | working for Claude Code |
| Hash-chained audit trail, verify and export | working |
| Process sandbox, hooks for other agents, HTTP MCP servers | not yet |

What Trackside does not do yet is said as plainly as what it does. The limits of each item are on the [website](https://tracksidehq.dev/#status).

## Trying it

The first demo build is out, for Macs with Apple silicon. Create a demo account on the [account page](https://tracksidehq.dev/account.html), then install the demo from the Terminal:

```sh
curl -fsSL https://tracksidehq.dev/install.sh | sh
```

The app is not notarized by Apple, which is why it is installed from the Terminal. The builds and the place for feedback are in the [trackside](https://github.com/tracksidehq/trackside) repository. Trackside is not open source.

## Built with

Rust for the core, which runs as its own process and owns the terminals, the policy decisions and the audit trail. Tauri 2 for the desktop shell. SolidJS, TypeScript and Vite for the interface. The gateway speaks the Model Context Protocol.
