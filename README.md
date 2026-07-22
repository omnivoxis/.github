# Omnivoxis

**An AI-native communication platform connecting phone networks, conferencing and messaging services, human operators, AI assistants, and MCP-enabled business tools through unified real-time sessions.**

---

## What we're building

Omnivoxis unifies phone calls, video conferencing, and messaging into a single real-time session model — with an AI assistant handling conversations, human operators supervising or taking over live, and MCP servers giving the AI policy-controlled access to calendars, CRMs, ticketing systems, and other business tools.

A single call can involve a caller on PSTN, an AI secretary, a human operator on WebRTC, a supervisor watching from Webex, and control commands arriving over Telegram — all as participants in one unified session.

Operators can send silent instructions to the AI mid-call ("ask the caller whether Wednesday afternoon works"), join a session, or take it over completely. The AI never acts on business systems directly — every action (booking a slot, rescheduling, canceling) is proposed as a structured intent and checked against policy before execution.

## Repositories

| Repo | Description |
|---|---|
| [`platform`](https://github.com/omnivoxis/platform) | Core platform for real-time communication orchestration, AI-assisted conversations, live human supervision, workflow automation, scheduling, administration, and session management. |
| [`connectors`](https://github.com/omnivoxis/connectors) | Communication adapters connecting Omnivoxis to telephony, conferencing, messaging, collaboration, and browser-based communication services. |
| [`mcp-servers`](https://github.com/omnivoxis/mcp-servers) | MCP servers providing policy-controlled access to calendars, contacts, email, CRM systems, scheduling services, ticketing platforms, and other business applications. |
| [`sdk`](https://github.com/omnivoxis/sdk) | Development kits, APIs, schemas, testing utilities, and reference implementations for building Omnivoxis connectors, MCP servers, clients, workflows, and agent extensions. |
| [`deployments`](https://github.com/omnivoxis/deployments) | Deployment configurations and operational tooling for local development, self-hosted installations, private cloud environments, and scalable production clusters. |
| [`docs`](https://github.com/omnivoxis/docs) | Product, architecture, integration, security, deployment, contributor, and user documentation for the Omnivoxis ecosystem. |

## How it fits together

```text
Communication layer          Business logic layer         Action layer
───────────────────          ─────────────────────        ───────────
connectors          ──────▶  platform                ───▶ mcp-servers
(transport)                  (session orchestration,       (policy-controlled
                              AI runtime, human-in-          business actions)
                              the-loop, workflows)
```

- **`connectors`** transport communication — they move audio, text, and events in and out of platforms like SIP, PSTN, WebRTC, Discord, Telegram, Webex, Microsoft Teams, Slack, and Matrix, each declaring the capabilities it supports (audio, messaging, call control, participant management, live events, operator commands).
- **`platform`** is where sessions live — it orchestrates conversations, runs the AI agent, handles live human supervision and takeover, manages scheduling and workflows, and enforces identity and policy.
- **`mcp-servers`** perform business actions — calendar bookings, CRM updates, ticketing — only after the platform's policy engine confirms the request is permitted (identity verified, action allowed, resource available, confirmation received).

## Getting started

- New to the project? Start with [`docs`](https://github.com/omnivoxis/docs) for architecture and the communication/session model.
- Want to build an integration? See [`sdk`](https://github.com/omnivoxis/sdk) for the connector SDK, MCP SDK, and testing utilities — you can build and test a new connector without needing a real phone line.
- Want to self-host? Check [`deployments`](https://github.com/omnivoxis/deployments) for Docker Compose (local/dev), single-server self-hosting, and Kubernetes (enterprise) setups.

## Contributing

We welcome contributions across all repositories — connectors for new communication platforms, MCP servers for business tools, workflow templates, and documentation improvements. See each repository's `CONTRIBUTING.md` for specifics, or the shared guidelines in this organization's [`.github`](https://github.com/omnivoxis/.github) repo.
