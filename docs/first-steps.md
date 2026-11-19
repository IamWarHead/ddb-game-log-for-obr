---
title: First steps
nav_order: 3
---

# First steps: connect your room

You do these steps once per room, as the GM, in the browser you normally use for Owlbear Rodeo.

## Open the extension

Click the Gamelog button in the toolbar. A small window opens with the **roll list** that everyone in the room sees. As GM you also get a **Settings** button and a **status dot** next to it. Hover the dot to read what it says, for example "Not set up" or "Connected".

{% include screenshot.html src="popover-gm.png" alt="The Gamelog window as GM: roll list, Settings button and status dot" %}

Click **Settings**. The settings window opens on the **Overview** page. While the setup is not finished it shows a **Finish setting up** checklist, and the Connection page in the menu carries a badge.

{% include screenshot.html src="settings-overview.png" alt="Settings, Overview page with the Finish setting up checklist" %}

## The welcome tour {#welcome-tour}

The first time you open a room with the extension as GM, a **Welcome to DDB Gamelog** window opens. It has four steps:

- **Welcome**: what DDB Gamelog does, and whether your browser relays the rolls or another GM's does.
- **Quick start**: the five steps on this page (log in, pick your campaign, link Patreon, link your characters, make a roll). Each step ticks itself off when it is done, and its button opens the right page and section of the settings. Steps that need the Gamelog server are marked **Needs connection** while you are not connected.
- **Membership**: your plan and what each plan includes.
- **What's new**: the highlights of the newest release.

The window opens every time until you click **Get started** on the last step or tick **Don't show again**. The answer is remembered per browser, for every room. Reopen the tour any time with **Welcome tour** on the **Overview** page of the settings.

After an update, the window opens once on the **What's new** step with what changed since the version you last ran, even if you ticked **Don't show again**.

Players get a shorter welcome of their own, see [For players]({{ '/players.html' | relative_url }}#welcome).

{: .note }
Only GMs have Settings. Players see the roll list only, see [For players]({{ '/players.html' | relative_url }}).

Open the **Connection** page.

{% include screenshot.html src="settings-connection.png" alt="Settings, Connection page" %}

## 1. Log in to D&D Beyond with your cobalt cookie

The cobalt cookie is a small piece of text that D&D Beyond gives your browser when you log in. It is called `CobaltSession`. Gamelog uses it to read your game log on your behalf.

To copy it:

1. Log in on [dndbeyond.com](https://www.dndbeyond.com).
2. Open your browser's developer tools (F12).
3. In Chrome, go to **Application**. In Firefox, go to **Storage**.
4. Open **Cookies**, then `https://www.dndbeyond.com`.
5. Copy the value of `CobaltSession`.
6. In **Settings → Connection**, paste it into the cobalt cookie field and click **Connect**.

{% include screenshot.html src="cobalt-cookie.png" alt="Cobalt cookie in the browser developer tools" %}

When it works, the page says which D&D Beyond user you are logged in as.

{: .note }
The cookie is stored only in this GM browser. It is never put in the room, never sent to your players and never shared. Treat it like a password: do not post it in Discord or in a screenshot.

{: .warning }
**Do not log out of D&D Beyond.** Logging out ends that session, and D&D Beyond hands out a new `CobaltSession` the next time you log in. The value Gamelog stored is dead from that moment, so rolls stop arriving until you copy the new one and connect again. Closing the browser or the tab is fine; only logging out breaks it.

Only one GM browser relays D&D Beyond rolls at a time. If another GM in the room already relays, your Settings show only **Take over** and the **Debug panel**, see [Only one GM relays]({{ '/troubleshooting.html' | relative_url }}#relaying-gm).

## 2. Pick your campaign

After you log in, your D&D Beyond campaigns appear on the Connection page, split into **You are the DM** and **You play in**. Pick the campaign whose game log should feed this room. It should be a campaign you are the DM of.

If your campaign is not listed, use **Reload the list** (the circular arrow). You can also open **Paste a campaign link instead** and enter the campaign address, for example `https://www.dndbeyond.com/campaigns/1234567`, or just its number.

{% include screenshot.html src="campaign-picker.png" alt="The campaign picker on the Connection page" %}

## 3. Link Patreon {#link-patreon}

Linking Patreon unlocks Basic, PRO or MAX features in this room, for everyone in it. You can skip this step: the Free tier works without it, see [Tiers]({{ '/tiers.html' | relative_url }}).

On the Connection page, scroll to **Membership** and click **Log in with Patreon**. When it works, the page says that the room is linked to your membership and shows its tier. Changes on Patreon apply within seconds.

{% include screenshot.html src="patreon-link-before.png" alt="The Membership section before linking Patreon" %}

{% include screenshot.html src="patreon-link-after.png" alt="The Membership section after linking Patreon" %}

{: .note }
No login window? Some browsers block it. The page then shows an **Open the Patreon login** link with a copy button: use either, in any browser. The login finishes on the Gamelog server, so the room is linked the moment you are done, even if you logged in on another device. See [Troubleshooting]({{ '/troubleshooting.html' | relative_url }}#patreon-window).

If you received a **product key** instead, enter it in **Product key (optional)** under Membership, see [Tiers]({{ '/tiers.html' | relative_url }}#product-keys).

The same Patreon account covers your Foundry worlds and your Owlbear Rodeo rooms.

## 4. Link your characters

Link the tokens of your players' characters to their D&D Beyond characters, so rolls, initiative and live stats land on the right token. See [Character linking]({{ '/features/character-linking.html' | relative_url }}).

## Check that it works

1. The status dot says **Connected**, and the **Status** section of the Connection page says the Gamelog server and the D&D Beyond game log are connected.
2. Roll something on D&D Beyond in the connected campaign.
3. A card appears in the roll list and in the corner of the map.

{% include screenshot.html src="first-roll.png" alt="A first roll in the Gamelog roll list and as a card on the map" %}

Nothing arrives? See [Rolls do not arrive]({{ '/troubleshooting.html' | relative_url }}#rolls-do-not-arrive).

## Settings are for the whole room

Settings you change apply to everyone in the room at once, and players have none of their own. The cobalt cookie and the product key are the exceptions: they stay in your browser.
