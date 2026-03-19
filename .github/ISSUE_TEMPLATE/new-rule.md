---
name: New rule proposal
about: Suggest a new DOM rule for a site
title: 'feat(DOMAIN): RULE_DESCRIPTION'
labels: 'new-rule'
assignees: ''
---

## Site

<!-- e.g. chat.openai.com -->

## What should the rule do?

<!-- Describe what element should be hidden/modified and why -->

## CSS Selector

<!-- The selector you tested in DevTools -->
```css
document.querySelectorAll('YOUR_SELECTOR_HERE')
```

## Proposed rule JSON
```json
{
  "id": "site-action-description",
  "name": "Site: description",
  "domains": ["example.com"],
  "action": "hide",
  "selector": ".your-selector",
  "disabled": false,
  "tags": ["print", "site-name"]
}
```

## Tested on

- [ ] Chrome
- [ ] Firefox
- [ ] Edge

## Screenshots (optional)

<!-- Before/after screenshots help reviewers -->