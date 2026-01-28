# FLock Provider Plugin for Moltbot

A Moltbot plugin that integrates [FLock API Platform](https://docs.flock.io/flock-products/api-platform/api-endpoint) as a model provider.

## Features

- OpenAI-compatible API integration
- API key authentication with secure storage in Moltbot auth profiles
- Automatic provider configuration

## Installation

```bash
moltbot plugins install @flock-io/moltbot-plugin-flock
```

Or if installing from a local path:

```bash
moltbot plugins install /path/to/moltbot-plugin-flock
```

## Configuration

### 1. Enable the Plugin

After installation, enable the plugin:

```bash
moltbot plugins enable flock
```

### 2. Authenticate

Run the authentication flow to store your FLock API key:

```bash
moltbot models auth login --provider flock
```

This will:
- Prompt for your FLock API key
- Store the key securely in Moltbot's auth profiles
- Configure the FLock provider in your Moltbot config

### 3. Add Models (Optional)

By default, the plugin configures an empty model list. You can add models in your Moltbot config:

```yaml
models:
  providers:
    flock:
      models:
        - id: qwen3-30b-a3b-instruct-2507
          name: Qwen 3 30B
          input: [text]
          contextWindow: 32768
          maxTokens: 4096
```

Or use the dynamic model format:

```bash
moltbot agent --model flock/qwen3-30b-a3b-instruct-2507
```

## Usage

Once configured, you can use FLock models with Moltbot:

```bash
# Use a specific FLock model
moltbot agent --model flock/your-model-id

# Or set as default in config
moltbot config set agents.defaults.model flock/your-model-id
```

## API Reference

- **Provider ID**: `flock`
- **Base URL**: `https://api.flock.io/v1`
- **API Type**: OpenAI-compatible (`openai-completions`)
- **Auth Header**: Standard `Authorization: Bearer <api-key>`

## Troubleshooting

### Authentication Issues

If you encounter authentication errors, verify:
1. Your API key is valid on [FLock Platform](https://flock.io)
2. The key is properly stored: check `~/.moltbot/auth-profiles.json`

### Model Not Found

If a model returns 404:
1. Verify the model ID exists on FLock
2. Check FLock documentation for available models

## Links

- [FLock API Documentation](https://docs.flock.io/flock-products/api-platform/api-endpoint)
- [FLock Platform](https://flock.io)
- [Moltbot Documentation](https://docs.molt.bot)

## License

Apache-2.0
