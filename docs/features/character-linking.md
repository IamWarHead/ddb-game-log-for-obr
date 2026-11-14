---
title: Character linking
parent: Features
nav_order: 3
---

# Character linking

**Tier:** Free for linking by hand. PRO for the party import.

Character linking tells Gamelog which token belongs to which D&D Beyond character. Without a link, a roll still shows in the roll list, but it cannot set initiative or update the token.

| What | Tier |
| --- | --- |
| Link tokens by hand: settings table, token menu | Free |
| Automatic link at the first initiative roll | Free |
| Dexterity typed per token | Free |
| Party import: link by name, add missing characters to your library | PRO |
| Dexterity read from D&D Beyond | PRO |

Tokens must be on the **Character** or **Mount** layer and be images. The link is stored on the token itself, so renaming the token does not break it, and it follows the token when you copy the scene.

## Link a token by hand (Free)

You need the **D&D Beyond character id**. It is the number at the end of the character's address on D&D Beyond: for `https://www.dndbeyond.com/characters/12345678` the id is `12345678`.

### From the settings

1. Open the scene with the tokens.
2. Open **Settings → Characters → Character linking**. The table lists every token of the open scene, linked tokens first.
3. In the **D&D Beyond character id** column, type the id or pick one of the suggestions: the campaign's characters, and characters seen in rolls. Clear the field to unlink.

{% include screenshot.html src="character-linking-table.png" alt="Settings, Characters page, the character linking table" %}

The **Character** column shows the linked character's name, or "not linked". The **Dex** column is for the [initiative tiebreaker]({{ '/features/initiative.html' | relative_url }}#dexterity-tiebreaker).

### From the token

Right-click a token and choose **Link to D&D Beyond character**. A window opens where you pick a character, enter an id and press **Link**, or press **Unlink** to remove the link.

{% include screenshot.html src="link-token-menu.png" alt="The token's right-click menu with Link to D&D Beyond character" %}

{% include screenshot.html src="link-dialog.png" alt="The Link token to D&D Beyond window" %}

The menu is for GMs only and works on one token at a time.

## Automatic link at the first initiative roll

A token that is not linked yet is linked when its character rolls initiative for the first time, but only if exactly one token in the scene has the character's name. With two tokens called "Guard" Gamelog never guesses.

A token you unlinked yourself is marked and is never linked by name again.

## Party import (PRO)

**Settings → Characters → Party import** does the linking for you. Run it in the browser of the GM who relays D&D Beyond rolls, with a campaign picked.

{% include screenshot.html src="party-import.png" alt="Settings, Characters page, the Party import section" %}

- **Import party** links every token of the open scene whose name matches exactly one character of the campaign. Tokens you place later are linked by their name too.
- **Add missing characters to the Characters panel** (on by default) also adds every character that has no token to your Owlbear Rodeo asset library as a Character, with the D&D Beyond avatar or a placeholder, so you can place it from the **Characters** panel. Owlbear Rodeo asks for a folder first: confirm with **Upload Images**. Importing again adds the characters again.
- **Show names on imported tokens** (on by default) puts the character name under imported and linked tokens. Off removes it from linked tokens of the open scene and from tokens linked later. Labels you wrote yourself are kept.

{% include screenshot.html src="party-import-assets.png" alt="The Owlbear Rodeo Characters panel with imported characters" %}

The import needs PRO. Without it the section shows an upgrade link.

## Wrong character linked?

See [Troubleshooting]({{ '/troubleshooting.html' | relative_url }}#the-wrong-character-is-linked).
