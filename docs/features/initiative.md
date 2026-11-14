---
title: Initiative
parent: Features
nav_order: 4
---

# Initiative

**Tier:** Free. Reading the Dexterity from D&D Beyond is PRO.

When a character rolls initiative on D&D Beyond, Gamelog can set the linked token's initiative in Owlbear Rodeo's **Initiative Tracker** extension. It is **off by default**: switch on **Set initiative from rolls** under **Settings → Characters → Initiative**.

{% include screenshot.html src="initiative-settings.png" alt="Settings, Characters page, the Initiative section" %}

You need:

- The official **Initiative Tracker** extension in your room.
- The character's token [linked]({{ '/features/character-linking.html' | relative_url }}) to the D&D Beyond character.

{% include screenshot.html src="initiative-tracker.png" alt="The Initiative Tracker with initiative set from a D&D Beyond roll" %}

Private initiative rolls count too. The tracker shows hidden tokens to the GM only.

## Settings

| Setting | What it does | Default |
| --- | --- | --- |
| Set initiative from rolls | An initiative roll from D&D Beyond sets the linked token's initiative | Off |
| Add tokens to the initiative tracker | Off: only tokens already in the tracker get the rolled initiative | On |
| Dexterity tiebreaker | Adds the Dexterity to the count, see below | Off |
| Show Dexterity on initiative roll cards | Initiative cards show the roller's Dexterity, for example Dex 14 (+2), for everyone in the room | Off |
| When the token already has initiative | **Ask me first**, **Replace it** or **Keep it** | Ask me first |

## Dexterity tiebreaker {#dexterity-tiebreaker}

Equal rolls are ordered by Dexterity.

| Option | Dex 14, roll 8 gives |
| --- | --- |
| Off | 8 |
| Dex score / 100 | 8.14 |
| Dex modifier / 10 | 8.2 |

The Dexterity comes from D&D Beyond with PRO. Without PRO, type it into the **Dex** column of the [character linking table]({{ '/features/character-linking.html' | relative_url }}); a score you type always wins.

{% include screenshot.html src="initiative-roll-card-dex.png" alt="An initiative roll card with the Dex tag" %}

## When the token already has initiative

With **Ask me first**, a window opens in the browser of the GM who relays rolls: **Replace initiative?** It says the token already has initiative and offers two buttons, **Keep** the old count or **Replace** it with the new one from D&D Beyond. Several questions wait in a queue; closing the window keeps every waiting token's initiative. A count of 0, which the tracker gives new tokens, counts as no initiative.

{% include screenshot.html src="replace-initiative-dialog.png" alt="The Replace initiative? window" %}
