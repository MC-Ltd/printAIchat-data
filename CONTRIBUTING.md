# Contributing to printAIchat-data

Thank you for helping improve printAIchat rules!

## How to add a new rule

1. Fork this repository
2. Edit `rules/rules.json`
3. Add your rule following the schema below
4. Test it locally (see Testing section)
5. Open a Pull Request

## Rule format

Every rule must have these required fields:

| Field      | Type     | Description                                      |
|------------|----------|--------------------------------------------------|
| `id`       | string   | Unique kebab-case ID, e.g. `chatgpt-hide-nav`    |
| `name`     | string   | Human-readable name (max 100 chars)              |
| `domains`  | string[] | Target domains, e.g. `["chat.openai.com"]`       |
| `action`   | string   | One of: `hide`, `remove`, `replace`, `addClass`, `inject` |
| `selector` | string   | Valid CSS selector                               |

Optional fields:

| Field         | Type    | Required for         | Description                   |
|---------------|---------|----------------------|-------------------------------|
| `value`       | string  | replace, addClass, inject | The replacement value    |
| `attribute`   | string  | replace              | HTML attribute to replace     |
| `type`        | string  | inject               | `css` or `js`                 |
| `description` | string  | —                    | What this rule does           |
| `disabled`    | boolean | —                    | Set true to disable           |
| `tags`        | array   | —                    | Categorization tags           |

## Action reference

| Action     | Description                            | Required extra fields |
|------------|----------------------------------------|-----------------------|
| `hide`     | Adds `display:none` via CSS class      | —                     |
| `remove`   | Removes elements from DOM              | —                     |
| `replace`  | Replaces text content or attribute     | `value`               |
| `addClass` | Adds CSS class(es) to elements         | `value`               |
| `inject`   | Injects CSS or JS string into the page | `type`, `value`       |

## Testing locally

1. Clone the extension repository
2. Point `GITHUB_RAW_BASE` in `constants.js` to your fork's raw URL
3. Load the extension in Chrome (see extension repo README)
4. Open the target site and check DevTools console for `[printAIchat]` logs
5. Use Options → Sync now to reload rules without restarting

## Selector tips

- Prefer `data-testid` attributes over class names (more stable)
- Test selectors in DevTools console: `document.querySelectorAll('your-selector')`
- Class names on AI chat sites change frequently — avoid them when possible
- Use `:is()` for grouping: `":is(nav, aside, .sidebar)"`

## Pull Request checklist

- [ ] Rule has a unique `id` in kebab-case
- [ ] CSS selector tested in DevTools on the target site
- [ ] `description` field explains what the rule does and why
- [ ] `disabled: false` (don't submit disabled rules)
- [ ] No sensitive data in rule values
- [ ] PR title format: `feat(domain): short description`