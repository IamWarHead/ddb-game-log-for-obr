---
title: Live token stats
parent: Features
nav_order: 5
---

# Live token stats

**Tier:** PRO. **Needs:** the free [Stat Bubbles for D&D](https://extensions.owlbear.rodeo/bubble-tracker) extension in your room.

Hit points and armor class of your linked tokens follow D&D Beyond: when a player's hit points change on their character sheet, the health bar on their token changes too.

{% include screenshot.html src="stat-bubbles-tokens.png" alt="Party tokens with health bars and armor class bubbles from Stat Bubbles for D&D" %}

Gamelog does not draw anything itself. It writes the numbers into Stat Bubbles, and Stat Bubbles draws the bars and bubbles.

## Set it up

1. Add **Stat Bubbles for D&D** to your room.
2. [Link]({{ '/features/character-linking.html' | relative_url }}) your players' tokens to their D&D Beyond characters.
3. Open **Settings → Integrations**, switch **Stat Bubbles** on and pick which stats to write. It is **off by default**, because it writes another extension's data.

{% include screenshot.html src="stat-bubbles-settings.png" alt="Settings, Integrations page, the Stat Bubbles section" %}

## What is written

One switch per stat:

| Stat | Where it shows |
| --- | --- |
| Current hit points | The health bar's current value |
| Maximum hit points | The health bar's maximum; Stat Bubbles shows the bar once it is above 0 |
| Temporary hit points | The temporary hit points bubble |
| Armor class | The armor class bubble |
| Name tag | The D&D Beyond character name, written when a token is linked. Shows when name tags are on in Stat Bubbles' settings |

## When it updates

- When a token is linked, when a scene opens and when you switch the integration on, Gamelog reads the stats fresh from D&D Beyond and fills them in.
- Then it keeps them live: whenever a stat changes on D&D Beyond, only that stat is written.
- Stats you change on the map stay until D&D Beyond changes them. Who may see them is still up to Stat Bubbles' **hide** switch.

The GM browser that relays D&D Beyond rolls does the writing, so it has to be open in the room.

## Without PRO

The switches are locked and show an upgrade link. See [Tiers]({{ '/tiers.html' | relative_url }}).
