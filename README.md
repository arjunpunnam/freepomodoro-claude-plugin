# Free Pomodoro for Claude

A Claude Code plugin that adds the [Free Pomodoro](https://www.freepomodoro.io) focus timer to Claude: start focus sessions, take breaks, and turn a goal into a step-by-step focus plan.

## Install

Requires [Claude Code](https://code.claude.com). No account or sign-in needed.

1. Add this marketplace:

   ```
   /plugin marketplace add arjunpunnam/freepomodoro-claude-plugin
   ```

2. Install the plugin:

   ```
   /plugin install freepomodoro@freepomodoro-marketplace
   ```

3. Restart Claude Code and run `/mcp` to check that **freepomodoro** is connected.

## Usage

Ask Claude in plain language:

- "Start a 25-minute pomodoro for my essay draft."
- "I have 2 hours to prepare for my chemistry exam. Make me a focus plan."
- "Give me a 10-minute break."

| Tool | What it does |
|---|---|
| `start_focus_timer` | Focus session, 1–180 min (default 25), with an optional label |
| `start_break` | Break countdown, 1–60 min (default 5); starts right away |
| `create_focus_plan` | Named plan of up to 12 tasks, each 1–180 min, with breaks in between |

The connector keeps nothing you type. Each timer returns a link that opens it in the Free Pomodoro web app. Focus sessions and plans wait until you press Start.

## Update or remove

```
/plugin marketplace update freepomodoro-marketplace
```

```
/plugin uninstall freepomodoro@freepomodoro-marketplace
```

## Troubleshooting

- **Tools don't appear:** restart Claude Code after installing, then check `/mcp`.

## Repository layout

```
.claude-plugin/marketplace.json     marketplace manifest
plugins/freepomodoro/               the plugin (points to https://www.freepomodoro.io/mcp)
docs/directory-listing.md           draft listing for Anthropic's connector directory
```
