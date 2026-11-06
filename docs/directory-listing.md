# Free Pomodoro: Claude connector directory listing

Listing for submitting `https://www.freepomodoro.io/mcp` to Anthropic's connector directory
(claude.ai/directory/manage → Submit new → MCP connector).

The connector is open: no account, no sign-in, and it keeps nothing users type.

## Listing text

**Name:** Free Pomodoro

**One-liner:**
> Start focus timers, breaks and Pomodoro study plans that run live in the chat. Free, with no sign-in.

**Long description:**
> Free Pomodoro turns "help me focus" into a timer you can actually start. Ask for a 25-minute session, a break, or a plan for the afternoon, and a live timer appears right in the chat with Start and Pause. Every timer also comes with a link that opens the same session in the Free Pomodoro web app, which adds ambient sounds, zen mode and a session history.
>
> What you can ask for:
> • A focus session from 1 to 180 minutes, with an optional label shown on the timer
> • A break from 1 to 60 minutes, which starts on its own
> • A focus plan: up to 12 named tasks, each with its own length, worked through one after another with 5-minute breaks in between. Give it a goal like "prepare for my chemistry exam in two hours" and it splits the time into concrete tasks.
>
> No account and no setup. The connector needs no sign-in and keeps nothing you type: each tool only builds a timer from what you asked for. Focus sessions and plans wait for you to press Start, so your browser lets the end-of-session chime play.
>
> What it can't do: the assistant can't check, pause or stop a timer after setting it up, and it can't see your focus history.

**Categories:** Productivity (primary), Education

**Example prompts:**

1. Start a 25-minute pomodoro on my essay introduction.
2. I have two hours to prepare for my chemistry exam. Make me a focus plan.
3. Plan my afternoon: inbox for 20 minutes, then two 45-minute blocks on the quarterly report.
4. Give me a 50/10 study session for flashcards.
5. I need a 5-minute break.

**Use cases:** students studying for exams; writers and developers blocking out deep work; anyone using the Pomodoro technique who wants to go from "what should I work on" to a running timer without leaving the chat.

**What users need before connecting:** nothing. No account, plan or API key.

**Reads or writes data:** neither. All three tools are read-only; they return a timer and a link and change nothing anywhere.

## Tools

Tools sync automatically from the server. Nothing should be flagged.

| Tool | Title | What it does | Annotations |
|---|---|---|---|
| `start_focus_timer` | Start a focus session | Focus session, 1–180 min (default 25), optional label | `readOnlyHint: true`, `openWorldHint: false` |
| `start_break` | Start a break | Break countdown, 1–60 min (default 5); starts right away | `readOnlyHint: true`, `openWorldHint: false` |
| `create_focus_plan` | Create a focus plan | Up to 12 tasks, each 1–180 min, with breaks in between | `readOnlyHint: true`, `openWorldHint: false` |

## Form fields

| Field | Value |
|---|---|
| Connection | `https://www.freepomodoro.io/mcp` (always `www`: the bare domain redirects, and MCP clients don't follow redirects on POST) |
| Slug | `free-pomodoro` (permanent once published) |
| Website | `https://www.freepomodoro.io/?utm_source=claude-directory` |
| Documentation | `https://www.freepomodoro.io/agents.html?utm_source=claude-directory` |
| Privacy policy | `https://www.freepomodoro.io/privacy.html` |
| Terms | `https://www.freepomodoro.io/terms.html` |
| Support contact | `contact@integrationinsightsinc.com` |
| Company | Integration Insights Inc., `https://www.freepomodoro.io` |
| Primary contact role | Founder |
| Icon | `web/public/icon-512.png` from the site repo (512×512 PNG) |
| Screenshots | 3–5 PNGs ≥ 1000px of the in-chat timer, each paired with an example prompt |
| Allowed link URIs | `https://www.freepomodoro.io` and `https://freepomodoro.io` |
| Authentication | **No authentication** |
| Data handling | Our own API. No personal health data. No sponsored content. |

**Test & launch notes for reviewers:**
> No account or credentials needed. Add `https://www.freepomodoro.io/mcp` as a custom connector, then try: (1) *Start a 25-minute pomodoro on my essay*: a timer card appears; press Start and it counts down; *Open in Free Pomodoro* opens the same timer on the website. (2) *Make me a two-hour plan for exam revision*: a plan card lists the tasks; Start runs them back to back with 5-minute breaks. (3) *I need a 5-minute break*: the break starts by itself. The server keeps no user data, so there is nothing to set up.

## Before submitting

- [ ] Test it as a custom connector in Claude and call all three tools; the form asks you to confirm this.
- [ ] `claude plugin validate ./plugins/freepomodoro` passes (for the plugin directory).

## References

- [Connector submission docs](https://claude.com/docs/connectors/building/submission)
- [Plugin submission](https://www.claude.com/docs/plugins/submit)
