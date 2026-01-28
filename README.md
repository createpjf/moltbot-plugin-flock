# FLock Provider Plugin for Moltbot

[![npm version](https://img.shields.io/npm/v/moltbot-plugin-flock.svg)](https://www.npmjs.com/package/moltbot-plugin-flock)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![GitHub](https://img.shields.io/badge/GitHub-FLock--io%2Fmoltbot--plugin--flock-blue?logo=github)](https://github.com/FLock-io/moltbot-plugin-flock)

> Use [FLock.io](https://flock.io) as your AI model gateway in Moltbot/Clawdbot

---

## What is This?

This plugin lets you use **FLock API Platform** as a model provider in [Moltbot](https://github.com/moltbot/moltbot) (also known as Clawdbot). 

**FLock** provides access to various AI models through an OpenAI-compatible API, making it easy to switch between different models without changing your code.

### Why Use FLock with Moltbot?

- Access to multiple AI models through one API
- OpenAI-compatible interface (works seamlessly with Moltbot)
- Competitive pricing and performance
- Easy API key authentication

---

## Prerequisites

Before you begin, make sure you have:

### 1. Moltbot Installed

If you haven't installed Moltbot yet, follow the [official installation guide](https://docs.molt.bot/install):

```bash
# macOS / Linux
curl -fsSL https://molt.bot/install.sh | bash

# Or via npm (requires Node.js 22+)
npm install -g moltbot
```

Verify installation:
```bash
moltbot --version
```

### 2. FLock API Key

You need an API key from FLock:

1. Go to [FLock.io](https://flock.io) and create an account
2. Navigate to your dashboard
3. Generate an API key
4. Keep this key safe - you'll need it during setup!

---

## Installation

### Step 1: Install the Plugin

```bash
moltbot plugins install moltbot-plugin-flock
```

You should see output like:
```
✓ Installed moltbot-plugin-flock
```

### Step 2: Enable the Plugin

```bash
moltbot plugins enable flock
```

### Step 3: Verify Installation

Check that the plugin is loaded:

```bash
moltbot plugins list
```

Look for `flock` in the list with status `loaded`.

---

## Configuration

### Authenticate with FLock

Run the authentication command:

```bash
moltbot models auth login --provider flock
```

You'll be prompted to enter your FLock API key:

```
◆ FLock API key
│ [paste your API key here]
```

After successful authentication, you'll see:
```
✓ FLock API configured at https://api.flock.io/v1.
```

Your API key is now securely stored in Moltbot's auth profiles.

---

## Usage

### Option 1: Use FLock Model Directly

Specify a FLock model when running Moltbot:

```bash
moltbot agent --model flock/qwen3-30b-a3b-instruct-2507
```

### Option 2: Set as Default Model

Make a FLock model your default:

```bash
moltbot config set agents.defaults.model flock/qwen3-30b-a3b-instruct-2507
```

Then simply run:
```bash
moltbot agent
```

### Option 3: Interactive Chat

Start a chat session with a FLock model:

```bash
moltbot agent --model flock/qwen3-30b-a3b-instruct-2507 --message "Hello! Tell me about yourself."
```

---

## Available Models

FLock provides access to various models. Use the format `flock/<model-id>`:

| Model ID | Description |
|----------|-------------|
| `qwen3-30b-a3b-instruct-2507` | Qwen 3 30B Instruct |
| `qwen3-235b-a22b-instruct-2507` | Qwen 3 235B Instruct |
| *(more models available)* | Check [FLock API Docs](https://docs.flock.io/flock-products/api-platform/api-endpoint) |

> **Tip:** Model availability may vary. Check the [FLock API documentation](https://docs.flock.io/flock-products/api-platform/api-endpoint) for the latest list.

---

## Advanced Configuration

### Adding Models to Config

For better autocompletion and model management, add models to your Moltbot config file (`~/.moltbot/config.yaml` or `~/.moltbot/moltbot.json`):

```yaml
models:
  providers:
    flock:
      baseUrl: https://api.flock.io/v1
      api: openai-completions
      models:
        - id: qwen3-30b-a3b-instruct-2507
          name: Qwen 3 30B
          input: [text]
          contextWindow: 32768
          maxTokens: 4096
        - id: qwen3-235b-a22b-instruct-2507
          name: Qwen 3 235B
          input: [text]
          contextWindow: 32768
          maxTokens: 4096
```

### Using with Different Channels

FLock works with all Moltbot channels:

- **WhatsApp**: Your WhatsApp bot uses FLock models
- **Telegram**: Telegram bot responses powered by FLock
- **Discord**: Discord bot with FLock intelligence
- **And more!**

---

## Troubleshooting

### "Provider not found"

Make sure the plugin is enabled:
```bash
moltbot plugins enable flock
moltbot plugins list  # Should show flock as "loaded"
```

### "Authentication failed" or 401 Error

Your API key might be invalid or expired:
```bash
# Re-run authentication
moltbot models auth login --provider flock
```

### "Model not found" or 404 Error

The model ID might be incorrect:
1. Check the exact model ID in [FLock documentation](https://docs.flock.io/flock-products/api-platform/api-endpoint)
2. Use the correct format: `flock/<model-id>`

### Check Your Configuration

View current config:
```bash
moltbot config get models.providers.flock
```

### View Logs

For detailed debugging:
```bash
moltbot doctor
```

---

## Updating the Plugin

To update to the latest version:

```bash
moltbot plugins update moltbot-plugin-flock
```

---

## Uninstalling

If you need to remove the plugin:

```bash
moltbot plugins disable flock
```

---

## Quick Reference

| Command | Description |
|---------|-------------|
| `moltbot plugins install moltbot-plugin-flock` | Install the plugin |
| `moltbot plugins enable flock` | Enable the plugin |
| `moltbot models auth login --provider flock` | Authenticate with FLock |
| `moltbot agent --model flock/<model-id>` | Use a FLock model |
| `moltbot plugins list` | Check plugin status |

---

## Links

- **FLock Platform**: https://flock.io
- **FLock API Documentation**: https://docs.flock.io/flock-products/api-platform/api-endpoint
- **Moltbot Documentation**: https://docs.molt.bot
- **Moltbot GitHub**: https://github.com/moltbot/moltbot
- **This Plugin on npm**: https://www.npmjs.com/package/moltbot-plugin-flock

---

## Support

- **FLock Issues**: Contact [FLock support](https://flock.io)
- **Plugin Issues**: [Open an issue](https://github.com/FLock-io/moltbot-plugin-flock/issues) on GitHub
- **Moltbot Issues**: [Moltbot GitHub Issues](https://github.com/moltbot/moltbot/issues)

---

## License

Apache-2.0 - See [LICENSE](LICENSE) for details.

---

<p align="center">
  Made with ❤️ by <a href="https://flock.io">FLock.io</a>
</p>
