<p align="center"><img src="icon.png" width="96" alt="Aimgod"></p>

# Aimgod MCP server

Your day planner, goals and focus inside Claude, ChatGPT, Cursor and any MCP client.

[Aimgod](https://aimgod.com) is a calm day planner for the web, iPhone and Apple Watch. This remote MCP server lets your AI read and plan your day: add tasks and habits, move them, break them into steps, build goal maps and keep the thoughts you live by in Focus. Everything you change shows up in the Aimgod app at once.

- **Server URL:** `https://app.aimgod.com/api/mcp`
- **Transport:** Streamable HTTP
- **Auth:** OAuth 2.1 with dynamic client registration. You sign in with your Aimgod account (Google, Apple or email) and choose what the client may do. No API keys.
- **Price:** free. An Aimgod account is free; Premium only adds more than 3 spheres and the smarter AI model inside the app.

## Connect

**Claude (web, desktop, iPhone):** Settings › Connectors › Browse connectors › Aimgod › Connect. Or Add custom connector with the server URL above.

**ChatGPT:** with developer mode on, add a custom connector with the server URL above.

**Cursor**, `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "aimgod": { "url": "https://app.aimgod.com/api/mcp" }
  }
}
```

**Claude Code:**

```bash
claude mcp add --transport http aimgod https://app.aimgod.com/api/mcp
```

**VS Code, Cline, Windsurf and other clients:** add a remote (HTTP) server with the URL above. The client opens the Aimgod sign in page the first time.

## What your AI can do

**Day and tasks:** `get_today`, `get_day_brief`, `get_tasks`, `show_day`, `add_task`, `update_task`, `delete_task`, `add_subtask`, `update_subtask`, `get_habit`.
Times, reminders, repeating tasks (habits), several spheres per task, starred tasks, moving to another day.

**Spheres (life areas):** `list_spheres`, `add_sphere`, `update_sphere`, `archive_sphere`.

**Goals:** `list_goals`, `add_goal`, `update_goal`, `delete_goal`, `update_subgoal`, `delete_subgoal`, `link_goals`, `unlink_goals`, `carry_over_goals`, `build_goal_flow`.
Month, quarter and year goals. An arrow from goal A to goal B keeps B locked until A is done; `build_goal_flow` lays out a whole path to a big goal.

**Focus:** `list_focus`, `add_focus_point`, `update_focus_point`, `delete_focus_point`.
Short points and quotes you keep in front of you, shown full screen in the app.

**Work handed to an AI agent:** `get_agent_work`, `start_task_work`, `finish_task_work`.
Turn on Claude in a task's window in Aimgod; the agent picks it up, does the work and leaves a link. You tick Done yourself.

**Interactive day card:** `aimgod_day` renders your day inside clients that support MCP UI.

**Prompts:** Plan my day, Empty my head, Evening review, Weekly review, My day with AI, Take my Aimgod work.

## Examples

- "Plan my day: gym at 7, two client calls, finish the landing page."
- "Move everything I didn't finish today to tomorrow morning."
- "Every weekday at 8:30, a 10 minute review of my goals."
- "I want to run a half marathon in April. Build the path as goals."
- "Add these five quotes to my Focus, in a sphere called Stoics."

## Privacy

The server sees only your own Aimgod data, after you sign in and approve the client. You can disconnect any client in the Aimgod menu › Connect to Claude. [Privacy Policy](https://aimgod.com/privacy) · [Terms](https://aimgod.com/terms).

## Support

hello@aimgod.com · [aimgod.com](https://aimgod.com) · [App Store](https://apps.apple.com/app/id1126844661)

The server's code lives in the Aimgod app repository, which is private. This repository holds the public description and the registry files.
