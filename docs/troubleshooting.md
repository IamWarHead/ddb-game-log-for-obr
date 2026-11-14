---
title: Troubleshooting
nav_order: 8
---

# Troubleshooting

If nothing here helps, report it, see [Feedback]({{ '/feedback.html' | relative_url }}).

Before you report a problem, open **Settings → Debug panel** and use **Copy support report**. It contains no cookies, keys or tokens. Paste it into your report. Players have no Settings button; ask your GM to copy it.

Then press **F12** in the browser that runs Owlbear Rodeo and look at the **Console** tab. Red lines there usually say what went wrong, and they belong in your report, see [Feedback]({{ '/feedback.html' | relative_url }}#errors-in-the-browser-console).

{% include screenshot.html src="debug-panel.png" alt="The Debug panel with the Copy support report button" %}

## It does not connect

Hover the status dot in the Gamelog window, or open **Settings → Connection** and read the message. Common ones:

| Message says | What to do |
| --- | --- |
| Not set up | Paste your cobalt cookie on the Connection page, see [First steps]({{ '/first-steps.html' | relative_url }}). |
| Invalid D&D Beyond cobalt | Log in on dndbeyond.com again and copy a fresh `CobaltSession` value, see [below](#cobalt-expired). |
| No campaign selected | Pick your campaign on the Connection page. |
| Campaign not found | Check that you picked the right campaign and that your account is its DM. |
| Server unreachable, Server did not respond | Try again in a few minutes. If it stays like this, ask on [Discord](https://discord.com/invite/HSTtrphyFg). |
| Extension outdated, reload | Reload the room in your browser, see [Install]({{ '/install.html' | relative_url }}#update). |
| Sign-in rejected, Session expired | Reload the room. If it stays, use **Reconnect** on the Connection page. |
| Invalid, expired or revoked product key | Check the key, or remove it under **Membership**. |
| Patreon unlinked | Log in with Patreon again, see [First steps]({{ '/first-steps.html' | relative_url }}#link-patreon). |
| Rate limited, retrying | Wait; Gamelog tries again by itself. |
| Wrong D&D Beyond account, D&D Beyond user limit reached, Too many connections, Access blocked | Ask on Discord. |

The **Status** section of the Connection page has a **Reconnect** button. If none of these fits, ask on Discord.

## Only one GM relays {#relaying-gm}

Gamelog reads your D&D Beyond game log through **one** GM browser at a time: the one that holds the cobalt cookie. That browser is the relay, and every player in the room gets the rolls through it.

- **The relaying browser must have the room open.** Close it, and rolls stop arriving for everyone until a GM relays again. Another GM with credentials saved takes over within seconds when it leaves.
- **Two tabs are two connections.** Do not open the same room twice in one browser.
- The **Overview** page says whether this browser or another GM's browser relays. The status dot shows **standby** when another GM's browser relays.

{% include screenshot.html src="popover-header-not-relaying.png" alt="The Gamelog window header with the status dot and the Not relaying tooltip" %}

- **Take over.** A second GM sees only **Take over** and the **Debug panel** in Settings. Enter your cobalt cookie, optionally a campaign link and a product key, and click **Take over relaying**. The relay moves to your browser, the other GM is told so, and the room's settings are then made in yours. Their browser only takes the relay back by itself when you leave the room.

{% include screenshot.html src="takeover-page.png" alt="The Take over page of a GM whose browser does not relay" %}

- Rolls then come from the campaign of **your** D&D Beyond login, and the features follow **your** membership, for everyone in the room.
- Settings that live on the server, like the Discord webhook, and the statistics records are set from, and kept in, the relaying GM's browser.

## Rolls do not arrive {#rolls-do-not-arrive}

Check these in order:

1. You are logged in to D&D Beyond (Connection page), and the status dot says **Connected**.
2. You picked the right campaign.
3. A GM browser is relaying and has the room open, see [above](#relaying-gm).
4. The roll is not private. Rolls sent to the DM or to self on D&D Beyond are not shown to players.
5. The roll type is in your tier. Monster rolls and rolls from the D&D Beyond player app need PRO, see [Tiers]({{ '/tiers.html' | relative_url }}).
6. For players: the GM has not switched off **Players see the roll history**; live cards still appear either way.
7. The cards are not hidden behind another extension. Change **Roll card corner** under **Settings → Rolls & cards**.

If you changed your Patreon membership, the change arrives within seconds. If your tier still looks wrong a minute later, reload the room.

## The Patreon login window does not open {#patreon-window}

Pressing **Log in with Patreon** opens a small window. A popup blocker stops it: Safari blocks pop-ups by default; Brave, uBlock Origin, AdGuard and similar extensions do the same.

The page then shows **Open the Patreon login** with a copy button next to it. Click the link, or copy it and paste it into any browser, your phone works too. The login is finished on the Gamelog server, so the room is linked the second you are done, and the page updates by itself.

The link is valid for 10 minutes. If it expires, press **Log in with Patreon** again for a fresh one.

## The cobalt cookie stopped working {#cobalt-expired}

The Connection page says D&D Beyond rejected the cobalt cookie, and rolls no longer arrive.

The usual cause is that you logged out on dndbeyond.com. Logging out ends that session for good: the next login gives your browser a **new** `CobaltSession`, and the value Gamelog saved cannot be used any more. The same happens if you log out everywhere from the D&D Beyond account settings, or change your password.

Simply closing the tab, closing the browser or restarting the computer does not do this. The cookie also ages out on its own after a while, so expect to repeat this now and then.

What to do: log in on [dndbeyond.com](https://www.dndbeyond.com), copy the fresh `CobaltSession` value, paste it into **Settings → Connection** and connect again, see [First steps]({{ '/first-steps.html' | relative_url }}). Your campaign, character links and settings are untouched.

{: .note }
If you have to log out of D&D Beyond, do it between sessions rather than during one, and copy the new cookie before you play.

## The wrong character is linked {#the-wrong-character-is-linked}

1. Open **Settings → Characters → Character linking**, or right-click the token and choose **Link to D&D Beyond character**.
2. Find the token and look at its **D&D Beyond character id** and the character name next to it.
3. Correct the id, or enter the right one. Clear the field to unlink.

See [Character linking]({{ '/features/character-linking.html' | relative_url }}).

## The character list or the table is empty

- The linking table lists the tokens of the **open scene** on the **Character** or **Mount** layer. Open a scene, and check the token's layer.
- The suggestions come from the campaign and from rolls seen so far. They appear when the relaying GM is connected to a campaign, or after a character's first roll. You can always type the id by hand.

## Initiative is not set

- **Set initiative from rolls** is off by default, see [Initiative]({{ '/features/initiative.html' | relative_url }}).
- The token must be linked, or be the only token with the character's name.
- The official Initiative Tracker extension must be in the room.
- With **Add tokens to the initiative tracker** off, only tokens already in the tracker get an initiative.
- With **Ask me first**, the question opens in the browser of the GM who relays rolls.

## Stat Bubbles shows nothing

- Needs PRO and the **Stat Bubbles for D&D** extension in the room, see [Live token stats]({{ '/features/live-token-stats.html' | relative_url }}).
- The **Stat Bubbles** switch under **Integrations** is off by default.
- The token must be linked, and the stat you want must be switched on.
- Stat Bubbles' own **hide** switch decides who may see the bars.

## A stat I changed on the map went back, or did not reach another scene

- **Keep map edits** under **Integrations → Stat Bubbles** must be on.
- A change of a stat synced from D&D Beyond lasts until that stat changes on D&D Beyond, see [Your changes on the map]({{ '/features/live-token-stats.html' | relative_url }}#your-changes-on-the-map).
- The relaying GM's browser must be open when you make the change, and the token must be linked.

## Statistics are missing rolls

Statistics are kept in the browser of the GM who relays. Rolls made while no GM browser had the room open are missing; fill the gap with **Import from D&D Beyond** (PRO), see [Statistics]({{ '/features/statistics.html' | relative_url }}#import-and-export-pro).

## The roll list is empty after a reload

Check that **Keep rolls after a reload** is on under **Settings → Rolls & cards → Roll history**, and that a GM did not use **Clear**. Players also need **Players see the roll history** switched on.
