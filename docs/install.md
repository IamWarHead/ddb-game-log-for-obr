---
title: Install
nav_order: 2
---

# Install

## Requirements

- An [Owlbear Rodeo](https://www.owlbear.rodeo/) account for the GM, who owns the room.
- A D&D Beyond account that is the DM of the campaign you want to connect.
- A Patreon membership if you want features above the Free tier, see [Tiers]({{ '/tiers.html' | relative_url }}).
- A current desktop browser for the GM. The GM's browser stays open during play, see [Only one GM relays]({{ '/troubleshooting.html' | relative_url }}#relaying-gm).

Players need nothing: no account on Gamelog, no extension, no membership.

## Add the extension

The extension is in alpha and is not in the Owlbear Rodeo extension store yet, so you add it with its manifest URL.

1. In Owlbear Rodeo, open your profile menu and choose **Add Extension**.
2. Paste this manifest URL and confirm:

   ```text
   https://obr.datapoint.hu/manifest.json
   ```

{% include screenshot.html src="install-add-extension.png" alt="The Add Extension dialog in Owlbear Rodeo with the manifest URL filled in" %}

3. Open your room, open its extensions list and switch **D&D Beyond Gamelog** on.

{% include screenshot.html src="install-room-extensions.png" alt="The room's extension list with D&D Beyond Gamelog switched on" %}

Once it is on, the Gamelog button appears in the toolbar of the room, for you and for every player.

{% include screenshot.html src="toolbar-button.png" alt="The Gamelog button in the Owlbear Rodeo toolbar" %}

{: .note }
The wording of Owlbear Rodeo's own menus can change. If a menu is not where this page says, look for the place where you add an extension by URL.

Next: [First steps]({{ '/first-steps.html' | relative_url }}).

## Several rooms

You add the extension to your account once. Switch it on in every room where you want it. Each room has its own settings, its own campaign and its own roll history.

## Update

You do not install updates. The extension is loaded from the address above, so a new version is used the next time the room is opened or reloaded.

If the extension tells you that your version is no longer supported ("Extension outdated, reload"), reload the room in your browser.

The extension shows its version on the Debug panel: **Settings → Debug panel**.

## Remove it

Switch the extension off in the room's extensions list, or remove it from your account. Your cobalt cookie and your roll records are kept in the GM's browser only. Clear the site data of the extension in your browser if you want them gone, see [Statistics]({{ '/features/statistics.html' | relative_url }}#where-the-numbers-come-from).
