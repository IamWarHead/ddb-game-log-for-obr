---
title: Statistics
parent: Features
nav_order: 7
---

# Statistics

**Tier:** Free teaser, Basic for the party at a glance, the highlights and the character table, PRO for everything else.

Dice statistics for your campaign, built from the rolls Gamelog relays from D&D Beyond. Open them in **Settings → Statistics**. Only GMs can open this page, so private rolls are included. There is no player view in Owlbear Rodeo.

| What | Tier |
| --- | --- |
| Session so far: rolls, natural 20s and 1s, most active roller | Free |
| Party at a glance, highlights, character table, range filter (latest session, 30 days, all time) | Basic |
| Monster table, Checks & saves, Combat and Luck tabs | PRO |
| d20 distribution and session charts | PRO |
| Luck awards, and luck per skill, ability and save | PRO |
| Session history and CSV / JSON export | PRO |
| Import past rolls from D&D Beyond, and from a file | PRO |
| Session recap to the roll list and to Discord, by hand or when a session ends | PRO |

## Where the numbers come from {#where-the-numbers-come-from}

- Every roll the relaying GM's browser sees is stored there, so **clearing the roll history does not erase the statistics**.
- Records are filed per D&D Beyond campaign. The page shows the current campaign, and asks you to pick one under Connection first if there is none.
- They are kept in the **GM's browser only**, because they include private rolls. A second GM, or a cleared browser, starts with its own (or no) history. On another GM's browser the page shows what that browser recorded while it relayed.
- Rolls from before the extension was set up, or made while no GM browser had the room open, are missing. **Import and export** on the Settings tab can fill that gap, see [Import and export](#import-and-export-pro).
- A new **session** starts after a 3-hour pause. The GM can also start one by hand, from the Sessions tab.

The statistics settings are kept in the GM's browser too, not in the room.

## The tabs

The **Time period** selector at the top picks the range: latest session, last 30 days, or all time. Checks & saves and Luck also have a **Character** selector (the whole party or one character), and so has the session history on the Sessions tab.

Charts have a y axis, and hovering a bar or a data point shows its exact value. Longer explanations sit behind a small info icon: hover or tab to it. Wide tables fit the settings window; long headings end in an ellipsis, so hover a heading for its full text.

- **Overview**: the party at a glance (total rolls, d20 average, natural 20s and 1s, damage dealt, healing done), highlights (highest and lowest d20 average, most natural 20s and 1s, biggest hit, most damage, most healing) and a table per character. With PRO, also a table for monsters and others.

{% include screenshot.html src="statistics-overview.png" alt="The Overview tab with highlights and the character table" %}

- **Checks & saves** (PRO): rolls by type, skills, ability checks and saving throws by ability, for the whole party or one character. Each table has a **Luck** column and a luck chart, see [Luck](#luck).

{% include screenshot.html src="statistics-checks.png" alt="The Checks and saves tab" %}

- **Combat** (PRO): attacks, damage, healing and death saves, per character and for the party. Counts are shown by default; switch on **Show percentages** in Settings to add shares.

{% include screenshot.html src="statistics-combat-1.png" alt="The Combat tab with the attacks and damage table" %}

{% include screenshot.html src="statistics-combat-2.png" alt="The combat charts and the healing and death saves table" %}

- **Luck** (PRO): how far each character's d20 average is above or below what the dice give on average, the luck awards and the d20 distribution chart, for the whole party or the character you pick.
- **Sessions** (PRO): session history with charts, starting a new session, and the recap.
- **Settings**: what is counted and shown, the automatic recap, **Import and export**, and **Reset statistics**.

{% include screenshot.html src="statistics-settings.png" alt="The Settings tab of the statistics page" %}

{: .note }
**There is no hit rate.** D&D Beyond rolls do not say what they were aimed at or whether they hit. The Combat tab shows the dice instead: attack d20 average, natural 20 and 1 shares, advantage and disadvantage use, damage and crits.

{: .note }
Rolls stored by earlier builds may have no roll type. They count in the totals and tables of the Overview, but not in Checks & saves, Combat or Luck, and the tabs tell you how many were left out.

## Locked tabs

Tabs your membership does not include show **made-up example rolls** with a banner that says so, so you can see what PRO adds. They are never stored, and your own rolls are not touched. On Free, the Overview tab shows the real session-so-far teaser.

## Luck

Luck is the d20 average minus the average the dice give for each roll's advantage mode. It evens out over many rolls. Per character it shows from 10 d20 rolls; until a character has that many, the Luck tab says so.

**Luck per skill** (PRO): on Checks & saves, every table has a Luck column, and each section a signed chart, using the same measure. It follows the **Character** selector, so you can see where one character's dice run hot or cold.

**Luck awards** (PRO) name the luckiest and toughest dice, and the longest hot streak (3 or more d20 rolls of 16 or higher in a row) and cold streak (3 or more of 5 or lower). They are **off by default** and only the GM sees them on the Luck tab. They reach the table only if you switch on **Name luck awards in the recap**, see [Session recap](#session-recap-pro). Ties get no award.

{% include screenshot.html src="statistics-luck-1.png" alt="The Luck tab with the Time period and Character selectors and luck per character" %}

{% include screenshot.html src="statistics-luck-2.png" alt="Luck awards and the d20 distribution on the Luck tab" %}

## Session recap (PRO)

The latest session as a summary: totals, highlights and the characters.

- **Post recap to the roll history** adds a recap card to the roll list of the room, for everyone. Only the GM browser that relays rolls can do it. You can also use the **Recap** button in the Gamelog window. The card shows the rolls, natural 20s and 1s, the highlights, and a row per character with rolls, d20 average, natural 20s and 1s, damage and healing; empty values are left out.
- **Post recap to Discord** needs the Discord integration, see [Discord]({{ '/features/discord.html' | relative_url }}). The embed shows the totals as large numbers, the highlights with an emoji each, and the party as an aligned table. It is in English.
- The Settings tab can post the recap by itself when a session ends: after a **3-hour pause without rolls**, or when you use **Start** under **Current session**. After a pause only the GM browser that relays the rolls posts, only for a session that ended in the last 24 hours, and only with at least 5 public rolls. Each session is posted once. Both automatic recaps are off by default.
- **Name luck awards in the recap** (PRO, off by default) adds the session's luckiest and toughest dice and hot and cold streaks. The whole table sees them, so they are opt-in.

Only **public rolls** are included, so private rolls never appear.

{% include screenshot.html src="statistics-sessions-recap.png" alt="The Current session and Session recap sections on the Sessions tab" %}

{% include screenshot.html src="statistics-recap-card.png" alt="The session recap card in the roll list" %}

{% include screenshot.html src="statistics-recap-discord.png" alt="The session recap as a Discord embed" %}

## Session history and current session (PRO)

The Sessions tab lists the latest sessions of the campaign with their rolls, natural 20s and 1s and the most active character, and charts the rolls, the d20 average and the luck per session once there are two. The **Character** selector narrows the charts to one character.

Sessions are spaced evenly on the charts, not by date, so a break in play does not show as a gap. A session without a value is a grey hollow mark: on the d20 average chart it had no d20 roll, on the luck chart fewer than 10. Hover the mark to see which.

Under **Current session**, **Start** counts rolls from now on as a new session. With the automatic recap switched on, the session that ends is posted first.

{% include screenshot.html src="statistics-sessions.png" alt="The Sessions tab with the history, charts and the current session" %}

## Import and export (PRO)

One section on the Settings tab, with three rows. Records are kept in this browser only, so this is also how you move statistics to another GM browser.

{% include screenshot.html src="statistics-import.png" alt="The Import and export section" %}

**Export** saves a file: **CSV** has one row per character or monster and session. **JSON** has the same figures and also keeps every roll of the campaign, private ones included, so it can be imported again.

**From D&D Beyond** reads the campaign's earlier rolls from D&D Beyond's game log and adds the ones this browser has not stored yet, so the statistics reach back before tracking began.

- Only the browser that relays D&D Beyond rolls can do it, and it needs a connection to the server and a picked campaign. Otherwise the button is disabled and says why.
- It walks back from the newest roll and shows how many rolls it read, how many were new and how far back it got. **Stop** ends it; what was already added stays.
- Rolls the browser already has are not counted twice, and private rolls meant for other players are never included.
- If D&D Beyond limits requests, it waits and tries again before it gives up. A run that stopped, failed or was limited carries on where it left off next time: the button then reads **Continue import from D&D Beyond**.
- An import can run **once an hour per campaign** and reads at most the **newest 1,000 rolls**. When it stops at 1,000, the page says so; older rolls are not read. Within the hour the button is disabled; hover it to see when it works again.

**From a file** imports a JSON export made with **Export JSON**, also one from another GM browser, and adds its rolls. Repeating it adds nothing. A file that is not a statistics export is refused without changing anything.

## Settings

- **Leave out short sessions**: sessions with fewer than 10 d20 rolls by player characters, such as a test or a few rolls between games, are left out of every tab, the session history, the charts and the export. Nothing is deleted; switch it off to count them again. Off by default.
- **Show percentages**: shares next to the counts in the Combat table. Off by default.
- **Show luck awards**: on the Luck tab, off by default (PRO).
- **Automatic recap** to the roll history and to Discord when a session ends, and **Name luck awards in the recap** (PRO).
- **Import and export**: see above.
- **Reset statistics**: a red button that deletes the roll records this browser stored for the current campaign. Click it twice to confirm. Cannot be undone, so export first if you want to keep them.

## Known limits

- Statistics are only as complete as what the GM's browser saw, see [Where the numbers come from](#where-the-numbers-come-from).
- The history is not shared between GM browsers: use **Import and export** to move it.
- The hourly import limit is kept on the server and starts again if the server restarts.
- The automatic recap after a pause only runs while the relaying GM browser has the room open: it posts when it next sees a session that ended within the last day.
- Without a membership that includes them, locked parts show a hint instead, see [Tiers]({{ '/tiers.html' | relative_url }}).
