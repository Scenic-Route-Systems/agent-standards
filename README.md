# agent-standards
A collection of agent standards, built up over time within my personal and professional use cases.

If all you need is high-level guidance for a Claude session in general, simply run `claude` within this project --
`CLAUDE.md` includes the basics from `general.md` and `development.md`.

For Claude Code within a specific project, instead commit a `.claude/settings.json` file. It can load the generic guidance, plus any relevant language and framework files. Note that many of the files are layered and additive, like including both `frameworks/tailwind.md` and `frameworks/tailwind-daisyui.md`.

The following example could be for a Python + Django + htmx + Alpine.js + Tailwind + daisyUI stack:

```json
{
  "$schema": "https://json.schemastore.org/claude-code-settings.json",
  "hooks": {
    "SessionStart": [
      {
        "matcher": "startup|clear|compact",
        "hooks": [
          {
            "type": "command",
            "timeout": 15,
            "command": "curl -fsSL --max-time 10 https://raw.githubusercontent.com/Scenic-Route-Systems/agent-standards/main/general.md || echo 'WARNING: shared standard general.md could not be fetched. Tell the user before starting work.'"
          },
          {
            "type": "command",
            "timeout": 15,
            "command": "curl -fsSL --max-time 10 https://raw.githubusercontent.com/Scenic-Route-Systems/agent-standards/main/development.md || echo 'WARNING: shared standard development.md could not be fetched. Tell the user before starting work.'"
          },
          {
            "type": "command",
            "timeout": 15,
            "command": "curl -fsSL --max-time 10 https://raw.githubusercontent.com/Scenic-Route-Systems/agent-standards/main/languages/python.md || echo 'WARNING: shared standard languages/python.md could not be fetched. Tell the user before starting work.'"
          },
          {
            "type": "command",
            "timeout": 15,
            "command": "curl -fsSL --max-time 10 https://raw.githubusercontent.com/Scenic-Route-Systems/agent-standards/main/frameworks/daisy.md || echo 'WARNING: shared standard frameworks/daisy.md could not be fetched. Tell the user before starting work.'"
          },
          {
            "type": "command",
            "timeout": 15,
            "command": "curl -fsSL --max-time 10 https://raw.githubusercontent.com/Scenic-Route-Systems/agent-standards/main/frameworks/django.md || echo 'WARNING: shared standard frameworks/django.md could not be fetched. Tell the user before starting work.'"
          },
          {
            "type": "command",
            "timeout": 15,
            "command": "curl -fsSL --max-time 10 https://raw.githubusercontent.com/Scenic-Route-Systems/agent-standards/main/frameworks/django-htmx-alpinejs.md || echo 'WARNING: shared standard frameworks/django-htmx-alpinejs.md could not be fetched. Tell the user before starting work.'"
          },
          {
            "type": "command",
            "timeout": 15,
            "command": "curl -fsSL --max-time 10 https://raw.githubusercontent.com/Scenic-Route-Systems/agent-standards/main/frameworks/django-tailwind-cli.md || echo 'WARNING: shared standard frameworks/django-tailwind-cli.md could not be fetched. Tell the user before starting work.'"
          },
          {
            "type": "command",
            "timeout": 15,
            "command": "curl -fsSL --max-time 10 https://raw.githubusercontent.com/Scenic-Route-Systems/agent-standards/main/frameworks/htmx-alpinejs.md || echo 'WARNING: shared standard frameworks/htmx-alpinejs.md could not be fetched. Tell the user before starting work.'"
          },
          {
            "type": "command",
            "timeout": 15,
            "command": "curl -fsSL --max-time 10 https://raw.githubusercontent.com/Scenic-Route-Systems/agent-standards/main/frameworks/tailwind.md || echo 'WARNING: shared standard frameworks/tailwind.md could not be fetched. Tell the user before starting work.'"
          },
          {
            "type": "command",
            "timeout": 15,
            "command": "curl -fsSL --max-time 10 https://raw.githubusercontent.com/Scenic-Route-Systems/agent-standards/main/frameworks/tailwind-daisyui.md || echo 'WARNING: shared standard frameworks/tailwind-daisyui.md could not be fetched. Tell the user before starting work.'"
          }
        ]
      }
    ]
  }
}
```