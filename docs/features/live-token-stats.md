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
- Who may see the stats is still up to Stat Bubbles' **hide** switch.

The GM browser that relays D&D Beyond rolls does the writing, so it has to be open in the room.

## Your changes on the map

Stat Bubbles keeps a separate copy of a token in every scene. With **Keep map edits** switched on (the default), Gamelog keeps your changes in step across them:

- **A stat synced from D&D Beyond:** a value you change on a linked token stays until D&D Beyond changes that stat. The character's tokens in the other scenes show your value too.
- **A stat switched off above:** Gamelog does not take it from D&D Beyond, but a value you change still reaches the character's tokens in the other scenes. Handy for tracking hit points by hand.
- **To drop a change**, set the stat back to D&D Beyond's value. A stat whose D&D Beyond sync you switch back on takes D&D Beyond's value again.

With **Keep map edits** off, D&D Beyond always wins: opening a scene shows D&D Beyond's values again, and your changes are forgotten.

Your changes are remembered in the relaying GM's browser. If another GM takes over the relay, they still show on the tokens you changed, but no longer reach the character's tokens in other scenes.

## Without PRO

The switches are locked and show an upgrade link. See [Tiers]({{ '/tiers.html' | relative_url }}).
