# Chronicles of the Skull Coast

A player-facing static campaign wiki. No dependencies, build process, or paid hosting required.

## Publish on GitHub Pages
1. Create a new public repository, e.g. `shadowdark-wiki`.
2. Extract the ZIP. Upload **the contents** of the extracted shadowdark-wiki folder to the repository root, keeping the folders intact. GitHub's web upload accepts files and folders; GitHub Desktop is another option.
3. Commit the files to `main`.
4. In repository Settings → Pages, select Deploy from a branch, `main`, `/ (root)`, then Save.
5. Open the site URL displayed in Settings → Pages once deployment completes.

## Update after each session
- Add a file such as `content/chronicles/session-02.md`. Copy the plain-text prose from Word, with blank lines between paragraphs.
- In `entries.json`, copy the preceding session's object, give it a unique id, title, path, and summary. Keep the list in chronological order. Set optional fields to null or an empty array where appropriate. The navigation is generated from this list.
- Update existing entries by editing their individual `.md` files. Update their `summary` in `entries.json` if you want the tooltip to change too.
- To add a new character, location, faction, or artifact, create a corresponding file and add a manifest object. The `aliases` array supplies extra terms that should link automatically, e.g. `Kanye`. Avoid common single-word aliases.
- Upload images under `images/` and set the entry's `image` field to its relative path. Click images to view them at full size. Character PDFs go in `sheets/` and use the `sheet` field.
- A `.md` file in this version is intentionally simple: blank-line-separated paragraphs, not a full Markdown renderer. No HTML is required. New entries require the single manifest edit above; GitHub Pages does not automatically list them.

## Local preview
From the extracted folder, run `python -m http.server 8000` and open http://localhost:8000 in a browser. Opening index.html directly will not work because browsers restrict local fetches.

## Player-facing safety
Everything in a public repository, including PDFs and older commits, is publicly accessible. Never upload GM-only notes, secrets, or private player information. The starter package uses the supplied campaign text and character sheets; review them before publishing.

## Design notes
Chronicles and world entries use the supplied prose; Kan-ye is standardized to Kayne, with Kanye retained as an alias. Character profiles and discovery entries summarize the supplied sheets and Session 1. Hop has a provisional entry from the narrative only. No portraits were invented. The title is provisional. Hover over highlighted terms for a short description, or click to open an entry. On touch screens, tap to open the entry. Search covers titles, aliases, summaries and prose.
