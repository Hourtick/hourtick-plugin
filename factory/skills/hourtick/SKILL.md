---
name: hourtick
description: Use when the user wants to track or log time, fill in a timesheet, see hours or billable totals, work with Hourtick tasks (by number, subtasks, blocked tasks), read or post in Hourtick team chat, or hand work to one of their team's AI agents in Hourtick.
---

# Hourtick

Hourtick is where a team and its AI agents plan work, talk about it and track the time it takes. The Hourtick MCP server acts with the signed-in person's own permissions, inside their workspace only.

## Start here

1. Call `whoami` first. It says who is signed in (a person or an AI agent), the workspace, the role and time zone, and what to do next.
2. Use names the user says, not IDs: projects, task types and clients are matched by name, tasks by number (`#12`).

## Time

- Find project and task type names with `list_projects`.
- Live tracking: `start_timer` and `stop_timer`; `get_running_timer` shows what's running.
- Time already spent: `log_time` with a duration like `1:30`, `1.5`, `90m` or `1h 30m` and a date. If it says the task type is ambiguous, ask the user which one.
- Totals: `get_report` by client, project, person or task type. `get_my_day` shows one day.
- Durations are hours and minutes; never show seconds.
- To help fill a timesheet, call `get_my_day`, propose entries, and log only the ones the user confirms.

## Tasks

- `list_tasks`, `create_task`, `update_task`, `comment_on_task`, `start_timer_on_task`, always by task number.
- Subtasks: `create_task` with `parent`. Dependencies: `blockedBy` on create, `addBlockedBy` / `removeBlockedBy` / `addBlocks` / `removeBlocks` on update. A blocked task can't move to in progress, review or done until its blockers are done; say so instead of retrying.

## Chat, notes and files

- Chat: `chat_list_channels`, `chat_read`, `chat_search`, `chat_post`. Posts notify people, so confirm the text with the user first.
- Notes and files on projects and clients: `list_notes`, `get_note`, `create_note`, `update_note` (prefer `appendMarkdown`), `list_files`, `read_file`, `add_file`.

## AI agents

- `list_agents` shows the team's agents and what they do. Hand one a task with `agent_delegate` and follow it with `get_agent_session`.
- Admins add and govern agents with `create_agent` and `update_agent`; anyone can ask for one with `request_agent`.

## Working as an agent

When `whoami` says you are an AI agent, the work you do can be billed, so account for it:

1. Take work with `agent_wait_for_work`, then read it with `agent_get_context` (your team's instructions come first).
2. Post short progress notes with `agent_log`; ask a person with `agent_ask` when you're blocked.
3. When done, log the time you worked with `log_time` on the task (or its project).
4. Finish with `agent_reply`, with your token usage and cost in `usage` when you know them. On Devin, leave cost out: Hourtick reads your ACUs from Devin.

## What Hourtick can't do here

- It can't delete time entries, send invoices, or reach other workspaces. Say so plainly and offer what it can do, such as a report of billable hours to invoice from.
- Time is always logged as the signed-in person or agent, never on someone else's behalf.

Setup for each AI app: https://hourtick.com/install.md
