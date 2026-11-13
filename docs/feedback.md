---
title: Feedback
nav_order: 9
---

# Feedback

There are two ways, and both are read:

| Where | Good for |
| --- | --- |
| [Discord](https://discord.com/invite/HSTtrphyFg) | Anything. Questions, "is this supposed to happen", quick reports. No GitHub account needed. |
| [GitHub issues](https://github.com/IamWarHead/ddb-game-log-for-obr/issues/new/choose) | A bug you can describe step by step, or an idea. The form asks for everything needed, so nothing gets lost. |

There are two forms: **Bug report** for something that does not work, and **Feedback or idea** for something that works but could be better.

## Discord

If you are not on the server yet, join it first: [https://discord.com/invite/HSTtrphyFg](https://discord.com/invite/HSTtrphyFg)

## What to include

- The extension version, for example 0.1.0. You find it on **Settings → Debug panel**.
- Your browser and its version.
- Whether you were the GM whose browser relays, another GM, or a player.
- What you did, step by step.
- What happened.
- What you expected to happen.
- Any red error from the browser console, see below.

## Errors in the browser console

Owlbear Rodeo runs in your browser, so most problems leave a message there. It is the single most useful thing you can send.

1. Press **F12** in the browser window that runs Owlbear Rodeo. On a Mac use **⌥⌘I** (Chrome, Edge) or **⌥⌘C** (Safari, after enabling the Develop menu).
2. Open the **Console** tab.
3. Reproduce the problem.
4. Copy the red lines.

A screenshot of the console works too. Keep the whole message, not only its first line: the part below it says where the error came from.

{: .note }
The console may also show errors from Owlbear Rodeo itself and from other extensions. Send what you see, we sort it out.

## Easy way

On the **Debug panel** use **Copy support report**. It copies a diagnostics report to your clipboard, with no secrets in it. Paste it into the form, or into your message on Discord.

## Do not share

Do not post any of these in Discord, in an issue, in screenshots or anywhere else:

- Your cobalt cookie (`CobaltSession`).
- A Discord webhook URL.
- A product key.
- Your email address.

The console prints network requests as well, so check a console screenshot for these before you post it.

Screenshots help a lot. Check them before you post.
