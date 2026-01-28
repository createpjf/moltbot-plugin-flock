```
    ███████╗██╗      ██████╗  ██████╗██╗  ██╗    ██╗  ██╗    ███╗   ███╗ ██████╗ ██╗  ████████╗██████╗  ██████╗ ████████╗
    ██╔════╝██║     ██╔═══██╗██╔════╝██║ ██╔╝    ╚██╗██╔╝    ████╗ ████║██╔═══██╗██║  ╚══██╔══╝██╔══██╗██╔═══██╗╚══██╔══╝
    █████╗  ██║     ██║   ██║██║     █████╔╝      ╚███╔╝     ██╔████╔██║██║   ██║██║     ██║   ██████╔╝██║   ██║   ██║   
    ██╔══╝  ██║     ██║   ██║██║     ██╔═██╗      ██╔██╗     ██║╚██╔╝██║██║   ██║██║     ██║   ██╔══██╗██║   ██║   ██║   
    ██║     ███████╗╚██████╔╝╚██████╗██║  ██╗    ██╔╝ ██╗    ██║ ╚═╝ ██║╚██████╔╝███████╗██║   ██████╔╝╚██████╔╝   ██║   
    ╚═╝     ╚══════╝ ╚═════╝  ╚═════╝╚═╝  ╚═╝    ╚═╝  ╚═╝    ╚═╝     ╚═╝ ╚═════╝ ╚══════╝╚═╝   ╚═════╝  ╚═════╝    ╚═╝   
    
    ⚡ Decentralized AI Gateway Provider ⚡           🦞 Your AI, Your Way 🦞
```

<p align="center">
  <a href="https://www.npmjs.com/package/moltbot-plugin-flock"><img src="https://img.shields.io/npm/v/moltbot-plugin-flock.svg?style=for-the-badge&logo=npm&logoColor=white&label=npm&color=CB3837" alt="npm version"></a>
  <a href="https://opensource.org/licenses/Apache-2.0"><img src="https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=for-the-badge" alt="License"></a>
  <a href="https://github.com/FLock-io/moltbot-plugin-flock"><img src="https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github" alt="GitHub"></a>
  <a href="https://platform.flock.io"><img src="https://img.shields.io/badge/FLock-Platform-6366f1?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyek0xMiAyMGMtNC40MSAwLTgtMy41OS04LThzMy41OS04IDgtOCA4IDMuNTkgOCA4LTMuNTkgOC04IDh6Ii8+PC9zdmc+" alt="FLock Platform"></a>
</p>

<p align="center">
  <b>🚀 Use FLock API Platform as your AI model gateway in Moltbot/Clawdbot 🚀</b>
</p>

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

### 1. Moltbot CLI Installed

If you haven't installed Moltbot yet, follow the [official installation guide](https://docs.molt.bot/install):

```bash
# Recommended: macOS / Linux one-liner
curl -fsSL https://molt.bot/install.sh | bash
```

**Or via npm** (requires Node.js 22+):
```bash
npm install -g moltbot@latest
```

> ⚠️ **Important:** Make sure to install `moltbot@latest` (version `2026.x.x`), NOT `moltbot@0.1.x`

**Verify installation:**
```bash
moltbot --version
# Should show: 2026.x.x
```

<details>
<summary>🔧 <b>Troubleshooting: "command not found"</b></summary>

If you see `zsh: command not found: moltbot`:

**Option 1: Use the full path**
```bash
# Find where npm installed it
npm list -g --depth=0

# The bin is usually at:
~/.nvm/versions/node/v22.x.x/bin/moltbot
# or
/usr/local/bin/moltbot
```

**Option 2: Fix your PATH (for nvm users)**
```bash
# Add to ~/.zshrc or ~/.bashrc:
export PATH="$HOME/.nvm/versions/node/$(node -v)/bin:$PATH"

# Then reload:
source ~/.zshrc
```

**Option 3: Use npx**
```bash
npx moltbot --version
```

</details>

### 2. FLock API Key

You need an API key from FLock API Platform:

1. Go to [FLock API Platform](https://platform.flock.io) and create an account
2. Navigate to your API Keys section
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

### 🧠 Reasoning / Thinking Models

| Model ID | Input Price | Output Price |
|----------|-------------|--------------|
| `qwen3-235b-a22b-thinking-2507` | $0.230 / 1M tokens | $2.300 / 1M tokens |
| `qwen3-235b-a22b-thinking-qwfin` | $0.230 / 1M tokens | $2.300 / 1M tokens |
| `kimi-k2-thinking` | $0.600 / 1M tokens | $2.500 / 1M tokens |

### 💬 Instruct / Chat Models

| Model ID | Input Price | Output Price |
|----------|-------------|--------------|
| `qwen3-30b-a3b-instruct-2507` | $0.200 / 1M tokens | $0.800 / 1M tokens |
| `qwen3-235b-a22b-instruct-2507` | $0.700 / 1M tokens | $2.800 / 1M tokens |
| `qwen3-30b-a3b-instruct-qmxai` | $0.200 / 1M tokens | $0.800 / 1M tokens |
| `qwen3-30b-a3b-instruct-coding` | $0.200 / 1M tokens | $0.800 / 1M tokens |
| `qwen3-30b-a3b-instruct-qmini` | $0.200 / 1M tokens | $0.800 / 1M tokens |

### 🚀 Other Models

| Model ID | Input Price | Output Price |
|----------|-------------|--------------|
| `deepseek-v3.2` | $0.280 / 1M tokens | $0.420 / 1M tokens |
| `deepseek-v3.2-dsikh` | $0.280 / 1M tokens | $0.420 / 1M tokens |
| `minimax-m2.1` | $0.300 / 1M tokens | $1.200 / 1M tokens |

> **💡 Tip:** Model availability and pricing may change. Check [FLock API Platform](https://platform.flock.io) for the latest list.

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
        # Reasoning models
        - id: qwen3-235b-a22b-thinking-2507
          name: Qwen 3 235B Thinking
          reasoning: true
          input: [text]
          contextWindow: 131072
          maxTokens: 8192
        - id: kimi-k2-thinking
          name: Kimi K2 Thinking
          reasoning: true
          input: [text]
          contextWindow: 131072
          maxTokens: 8192
        # Instruct models
        - id: qwen3-30b-a3b-instruct-2507
          name: Qwen 3 30B Instruct
          input: [text]
          contextWindow: 131072
          maxTokens: 8192
        - id: qwen3-30b-a3b-instruct-coding
          name: Qwen 3 30B Coding
          input: [text]
          contextWindow: 131072
          maxTokens: 8192
        # DeepSeek
        - id: deepseek-v3.2
          name: DeepSeek V3.2
          input: [text]
          contextWindow: 131072
          maxTokens: 8192
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

- **FLock API Platform**: https://platform.flock.io
- **FLock API Documentation**: https://docs.flock.io/flock-products/api-platform/api-endpoint
- **Moltbot Documentation**: https://docs.molt.bot
- **Moltbot GitHub**: https://github.com/moltbot/moltbot
- **This Plugin on npm**: https://www.npmjs.com/package/moltbot-plugin-flock

---

## Support

- **FLock Issues**: Contact [FLock support](https://platform.flock.io)
- **Plugin Issues**: [Open an issue](https://github.com/FLock-io/moltbot-plugin-flock/issues) on GitHub
- **Moltbot Issues**: [Moltbot GitHub Issues](https://github.com/moltbot/moltbot/issues)

---

## License

Apache-2.0 - See [LICENSE](LICENSE) for details.

---

<p align="center">
  Made with ❤️ by <a href="https://flock.io">FLock.io</a>
</p>
