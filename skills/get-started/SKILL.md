---
name: get-started
description: Set up or check GWC Bridge in Grok Build with the user's existing GWC account, intended computer and shared folder, then confirm one harmless file read without changing access, editing files, running commands or starting tasks.
---

# Get started with GWC Bridge

Use this workflow when the user connects GWC Bridge, asks whether it is ready, or needs to recover a connection. Do not use it as a preflight for unrelated requests: answer ordinary questions about text the user supplied without calling any GWC Bridge tool.

## What the user needs

- A GWC account with an active Connect Pass.
- GWC Studio or GWC for VS Code installed on the intended computer, signed in with the same GWC account, with Bridge switched on. The computer must be on and online.
- At least one folder shared with Bridge from that desktop app.

Installing this plugin does not install the desktop app or connect a computer. Signing in to GWC from Grok Build does not by itself prove that Bridge can read a file. Public guide: https://gwc-corp.com/bridge

## First read

1. **Account and computer.** Call `who_am_i`, then `list_devices` and `get_status`. If several computers are listed, let the user choose; never substitute another online computer.
2. **Folder.** Call `list_folders` and use only a folder ID it returned for that computer. A capability that a response does not report is unknown, not enabled.
3. **File.** Use a non-sensitive text file the user names, or browse only that folder with `list_files`. Do not search the whole computer or open secret files.
4. **Read.** Call `read_file` with the folder ID, the relative path and a small range. Report the text actually returned and say if it was truncated.
5. **Result.** Only after content comes back, say "First read confirmed in Grok Build" with the computer, folder and file. This confirms that one read, not every Bridge feature.

During this check, do not edit files, run commands, start processes or agent tasks, or change settings.

## Access and permissions

The owner controls access on the computer, in GWC Studio or GWC for VS Code: which folders are shared, whether each folder allows changes, and whether commands and agent tasks are allowed. Bridge cannot grant itself more access. If the user asks to share another folder or enable commands, explain that this is done in the desktop app; do not try to change it with a tool. `set_pc_settings` cannot add folders or enable capabilities.

Commands, interactive processes and agent tasks run with the user's own account rights on that computer and are not confined to the shared folders. Run them only when the user explicitly asks.

## Errors

- `CONNECT_PASS_REQUIRED`: stop and say "Your GWC account does not currently have an active Connect Pass." Do not guess the reason.
- A computer that is offline or not listed: ask the user to open GWC Studio or GWC for VS Code on it, signed in with the same account.
- A refused tool call: do not retry it automatically or switch to another computer, folder or account.
