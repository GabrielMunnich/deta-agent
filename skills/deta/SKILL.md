---
name: deta
description: Work in Deta (deta.studio), the drawing review and takeoff app for architecture, engineering and construction, through the Deta CLI. Use when the user mentions Deta, pastes a deta.studio link, or asks to read, create or edit drawing markups, takeoff tables, page scales, presets, templates or product libraries in Deta.
---

# Deta

The Deta CLI reads and writes drawings, markups, takeoff tables, page scales and product libraries with the user's own Deta permissions.

## Run the CLI

Run it as `npx -y @deta-studio/cli@latest <args>` (Node 20 or later). Below, `deta` stands for `npx -y @deta-studio/cli@latest`. Sandboxed agents such as Codex need network access approved for these commands.

## Connect

1. Run `deta status` to see the signed-in account, the server and the selected drawing.
2. If nobody is signed in, ask the user for the email of their Deta account and run `deta login --email <email>`. Deta emails them a sign-in code: ask for it, then run `deta login --email <email> --code <code>`. The sign-in stays on this computer for later chats. `deta login` alone signs in through the browser instead.
3. Run `deta open <drawing URL>` to select the drawing for commands run in this directory. Ask the user for the drawing link when none is selected.

To sign out, run `deta logout`.

## Learn the contract

- `deta help` lists the commands, and `deta help <command>` gives exact arguments.
- `deta guide` lists the topics; read `deta guide <topic>` for your task before you write.
- `deta schema <name>` prints the JSON schema for a payload.
- The API reference is at https://www.deta.studio/docs/api.

## Read and write

- Read the current state first, and keep unrelated work and stable IDs as they are.
- Write each payload to a JSON file and pass its path to the command.
- Check markup changes with `"dryRun": true` in the payload, then publish them without it.
- A 409 means the drawing changed since you read it: re-read, merge your change into the current state and retry.
- Read back what you saved, and tell the user what changed and where.
