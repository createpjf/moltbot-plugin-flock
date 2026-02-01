# @openclawd/flock

[FLock API Platform](https://platform.flock.io) provider plugin for [OpenClaw](https://openclaw.ai).

[![npm](https://img.shields.io/npm/v/@openclawd/flock.svg)](https://www.npmjs.com/package/@openclawd/flock)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

## Install

```bash
openclaw plugins install @openclawd/flock
openclaw plugins enable flock
```

## Setup

1. Get an API key from [FLock API Platform](https://platform.flock.io)
2. Authenticate:

```bash
openclaw models auth login --provider flock
```

## Usage

```bash
openclaw agent --model flock/qwen3-30b-a3b-instruct-2507
```

Or set as default:

```bash
openclaw config set agents.defaults.model flock/qwen3-30b-a3b-instruct-2507
```

## Available Models

### Reasoning

| Model ID | Input | Output |
|----------|-------|--------|
| `qwen3-235b-a22b-thinking-2507` | $0.23/M | $2.30/M |
| `qwen3-235b-a22b-thinking-qwfin` | $0.23/M | $2.30/M |
| `kimi-k2-thinking` | $0.60/M | $2.50/M |

### Instruct

| Model ID | Input | Output |
|----------|-------|--------|
| `qwen3-30b-a3b-instruct-2507` | $0.20/M | $0.80/M |
| `qwen3-235b-a22b-instruct-2507` | $0.70/M | $2.80/M |
| `qwen3-30b-a3b-instruct-coding` | $0.20/M | $0.80/M |

### Other

| Model ID | Input | Output |
|----------|-------|--------|
| `deepseek-v3.2` | $0.28/M | $0.42/M |
| `minimax-m2.1` | $0.30/M | $1.20/M |

> Pricing may change. See [FLock API Platform](https://platform.flock.io) for the latest.

## Compatibility

| Platform | Version |
|----------|---------|
| **OpenClaw** | `>= 2026.1.29` |
| Moltbot | `>= 2026.1.0` |
| Clawdbot | `>= 2026.1.0` |

## Links

- [FLock API Platform](https://platform.flock.io)
- [FLock API Docs](https://docs.flock.io/flock-products/api-platform/api-endpoint)
- [OpenClaw](https://openclaw.ai)
- [Issues](https://github.com/FLock-io/moltbot-plugin-flock/issues)

## License

Apache-2.0
