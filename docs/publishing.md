# Publishing as a Claude artifact

Second Nature runs on its own from a file, but it is at its best published as a Claude artifact, where it gets a database that follows you between devices.

## Steps

1. Open [claude.ai](https://claude.ai) and start a conversation in Claude Code (web, desktop or CLI).
2. Give Claude the `second-nature.html` file from this repository and ask it to publish the file as an artifact with the `db`, `user`, `sample` and `downloads` capabilities.
3. Open the link Claude gives you. That link is the app. Bookmark it, or add it to your phone's home screen.
4. Later changes: ask Claude to update the same artifact in place, so the link and your data stay put.

## What each capability does

| Capability | Used for | Without it |
|---|---|---|
| `db` | All your chunks, quests, days, chapters and settings, kept in the artifact's database. | The page saves to the browser you're using, and only there. |
| `user` | Your private folder in the database. A recall session you leave part-way is saved there so another device can pick it up. | The paused session is kept on the device only. |
| `sample` | On Recall, "Check my answer" sends what you typed plus your notes to Claude and shows a short check. Uses your own Claude usage; asks once per page load. | The button is hidden. |
| `downloads` | The backup buttons at the bottom of Recall. | The buttons are hidden inside an artifact (in a plain browser tab they still work). |

## Data

Everything is stored as small JSON documents:

- `chunks/<id>` — one document per chunk, including its practice cards and links to other chunks.
- `inbox/<id>` — captured ideas not yet turned into chunks.
- `quests`, `events`, `days`, `runs`, `chapters`, `bosses`, `items`, `expeditions`, `traits` — the quests game.
- `meta/<name>` — small settings documents (your character's name, what has been seeded).
- `data/users/<you>/recall` — the paused recall session, private to you.

Claude can read and write these documents for you from a conversation (for example, to import chunks in bulk), and the JSON backup from the Recall page holds the chunks and inbox.
