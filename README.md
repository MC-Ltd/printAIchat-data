# printAIchat-data

Data repository for the [printAIchat](https://github.com/YOUR_USERNAME/printAIchat)
browser extension.

Contains rules, patches, locales, and config that the extension
downloads and caches locally. Updates here take effect within minutes
— no extension update required.

## Structure

| Path | Description |
|------|-------------|
| `rules/rules.json` | DOM manipulation rules for all supported sites |
| `rules/schema/` | JSON Schema for validation |
| `patches/` | Per-site CSS/JS patches |
| `locales/` | i18n message files |
| `config/defaults.json` | Default extension settings |

## Supported sites

| Site | Domain |
|------|--------|
| ChatGPT | `chat.openai.com` |
| Claude | `claude.ai` |
| Gemini | `gemini.google.com` |
| Microsoft Copilot | `copilot.microsoft.com` |
| Mistral | `chat.mistral.ai` |
| Poe | `poe.com` |

## Raw URLs (used by extension)
```
https://raw.githubusercontent.com/YOUR_USERNAME/printAIchat-data/main/rules/rules.json
https://raw.githubusercontent.com/YOUR_USERNAME/printAIchat-data/main/config/defaults.json
https://raw.githubusercontent.com/YOUR_USERNAME/printAIchat-data/main/locales/en/messages.json
https://raw.githubusercontent.com/YOUR_USERNAME/printAIchat-data/main/locales/uk/messages.json
```

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for how to add rules.

## License

MIT — rules and patches are freely usable.