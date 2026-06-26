# Hermes Agent ARM64 for Coolify

A production-ready Docker Compose template for deploying **Hermes Agent** on **ARM64** systems such as:

* Oracle Cloud Free Tier (Ampere A1)
* Raspberry Pi 4/5
* Apple Silicon (Docker Desktop)
* Other ARM64 Linux servers

This template runs **Hermes Agent only** (without the Hermes WebUI), making it lightweight and ideal for AI agents running through Telegram, Discord, MCP, APIs, or automation platforms like n8n.

---

## Features

* ✅ ARM64 compatible
* ✅ Hermes Agent only (no WebUI)
* ✅ Persistent Docker volumes
* ✅ Automatic restart (`unless-stopped`)
* ✅ Health checks
* ✅ Graceful shutdown
* ✅ Easy cloning for multiple Hermes instances
* ✅ Coolify compatible

---

## Requirements

* Docker
* Docker Compose
* Coolify (recommended)
* ARM64 Linux

---

## Environment Variables

Copy `.env.example` to `.env` and configure your values.

Required:

```env
CONTAINER_NAME=hermes-personal

HERMES_VOLUME_HOME=hermes-personal-home
HERMES_VOLUME_SRC=hermes-personal-src
HERMES_VOLUME_WORKSPACE=hermes-personal-workspace
```

Optional AI Provider Keys:

```env
OPENROUTER_API_KEY=
OPENAI_API_KEY=
ANTHROPIC_API_KEY=
GOOGLE_API_KEY=
```

Only configure the providers you intend to use.

---

## Deployment with Coolify

1. Create a new **Docker Compose** resource.
2. Paste the contents of `docker-compose.yml`.
3. Add your environment variables.
4. Deploy.

---

## Creating Multiple Hermes Instances

This template is designed for running multiple independent Hermes Agents.

Example:

| Instance    | Container       | Home Volume          |
| ----------- | --------------- | -------------------- |
| Personal    | hermes-personal | hermes-personal-home |
| Development | hermes-dev      | hermes-dev-home      |
| Research    | hermes-research | hermes-research-home |

Each instance has its own configuration and workspace.

---

## Repository Structure

```
.
├── docker-compose.yml
├── .env.example
├── README.md
├── LICENSE
└── .gitignore
```

---

## Disclaimer

This repository provides an ARM64 deployment template only.

Hermes Agent is developed and maintained by the Hermes project contributors. Please refer to the official Hermes documentation for application-specific features and updates.

---

## License

[MIT License](https://github.com/darvax/coolify-hermes-agent-arm64?tab=MIT-1-ov-file)
