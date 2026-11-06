# Free Pomodoro: Claude connector directory listing

Draft listing for submitting `https://www.freepomodoro.io/mcp` to Anthropic's connector directory.
Items in **[brackets]** still need to be filled in.

## Listing text

**Name:** Free Pomodoro

**Tagline:** Focus timers, breaks and step-by-step study plans, right in your chat.

**Category:** Productivity

**Full description:**

> Free Pomodoro brings the Pomodoro technique into Claude. Ask Claude to start a focus session ("start a 25-minute pomodoro on my essay"), take a break, or turn a goal like "prepare for my chemistry exam in two hours" into a focus plan. A focus plan is a list of tasks, each with its own focus time, worked through one by one with breaks in between.
>
> The timer appears live in the chat with Start and Pause buttons where your Claude app supports it. Every timer also comes with a link that opens it in the Free Pomodoro web app. Focus sessions and plans wait until you press Start. Breaks start right away.
>
> Sign in with your Free Pomodoro account to use the connector.

**Example prompts:**

1. "Start a 25-minute pomodoro for my essay draft."
2. "I have 2 hours to prepare for my chemistry exam. Make me a focus plan."
3. "Give me a 10-minute break."
4. "Plan my afternoon: 50 minutes on the report, 30 on emails, 25 on code review."

## Tools

| Tool | Title | What it does | Annotations |
|---|---|---|---|
| `start_focus_timer` | Start focus timer | Sets up a focus session (1–180 min, default 25) with an optional label | `readOnlyHint: false`, `destructiveHint: false` |
| `start_break` | Start break | Starts a break countdown (1–60 min, default 5) | `readOnlyHint: false`, `destructiveHint: false` |
| `create_focus_plan` | Create focus plan | Creates a named plan of up to 12 tasks, each 1–180 min, with breaks in between | `readOnlyHint: false`, `destructiveHint: false` |

## Submission details

- Server URL: `https://www.freepomodoro.io/mcp`
- Website: `https://www.freepomodoro.io`
- Docs page: https://github.com/arjunpunnam/freepomodoro-claude-plugin#readme
- Privacy policy: https://www.freepomodoro.io/privacy.html
- Terms of service: **[URL]**
- Support contact: contact@integrationinsightsinc.com
- Company: Integration Insights Inc.
- Slug: `freepomodoro`
- Icon: **[square PNG/SVG logo]**
- Test account for reviewers: **[email + password for an account with no real data — share in the submission form only, never commit it here]**

## Pre-submission checklist

- [ ] Every tool has a `title` and `readOnlyHint` / `destructiveHint` annotations, e.g. (TypeScript MCP SDK):

  ```ts
  server.registerTool("start_focus_timer", {
    title: "Start focus timer",
    description: "...",
    inputSchema: { /* ... */ },
    annotations: { readOnlyHint: false, destructiveHint: false, openWorldHint: false },
  }, handler);
  ```

- [ ] `/mcp` returns `401` with a `WWW-Authenticate` header to anyone who isn't signed in.
- [ ] OAuth discovery info is published at `/.well-known/oauth-protected-resource`.
- [ ] `https://claude.ai/api/mcp/auth_callback` is an allowed OAuth redirect URL.
- [ ] Server instructions and listing both say that sign-in is required.
- [ ] Privacy policy covers Google sign-in, Cloudflare, data retention, and what the Claude connector sends and receives.
- [ ] `claude plugin validate ./plugins/freepomodoro` passes.

## References

- [Connector submission docs](https://claude.com/docs/connectors/building/submission)
- [Connector directory](https://claude.com/docs/connectors/directory)
- [Plugin submission](https://www.claude.com/docs/plugins/submit)
