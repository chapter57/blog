# Longhand

A quiet place to write, and a little company while you do: a free writing app, a monthly almanac for writers, and an occasional essay on craft.

The site is built by GitHub Pages from this project. Changes go live a minute or two after they reach the `gh-pages` branch. Readers write to longhandlit@gmail.com (set as `email` in `_config.yml`).

## What's where

- `index.html`: the front page, with the app, the current Almanac, the essays and "Write to us"
- `_almanac/`: one file per Almanac issue, named by month (`2026-10.md`)
- `_essays/`: one file per craft essay; `how-to-add-an-essay.md` is a template
- `_layouts/`, `_includes/`, `assets/site.css`: the page design; the drawings (pen, moon phases, postmark, envelope, ink rule) are in `_includes/ill-*.html`
- `_config.yml`: site settings
- `fonts/`: Literata and IBM Plex Mono, both under the SIL Open Font License (see `fonts/OFL.txt`)
- `write/`: the Longhand writing app
- `sw.js`: retires the offline copy that older installs of the app kept at the site's main address

## A new Almanac issue

1. Copy last month's file in `_almanac/` and name the copy by the new month, like `2026-11.md`.
2. Change `number`, `month`, the prompt lines, and the open calls. Each open call has a `name`, `what`, `deadline` and `url`; leave `open_calls: []` for a month without any.
3. Replace the note under the second `---` line with this month's note from the editor.

The front page always shows the newest issue in full and lists the older ones. Each issue also has its own page at `longhandlit.com/almanac/2026-11/`.

## A new essay

1. Copy `_essays/how-to-add-an-essay.md` to a new file with a short name, like `_essays/on-revision.md`.
2. Fill in the title, one-sentence description (`dek`), author and date, and paste the essay underneath.
3. Delete the `published: false` line.

It appears in the Essays section of the front page, newest first, with its own page at `longhandlit.com/essays/on-revision/`.

## The Almanac by email

When you set up an email edition at [Buttondown](https://buttondown.com), put your username in `newsletter_username` in `_config.yml`, and a sign-up box replaces the "write to us to be added" note on the front page.

## The domain

The site lives at [longhandlit.com](https://longhandlit.com), registered at Namecheap. The `CNAME` file tells GitHub Pages to serve it there, and `url` in `_config.yml` matches.

DNS records for the website:

| Type | Host | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | chapter57.github.io |

The writing app keeps pieces per address, so anyone who used it at an earlier address should Export their pieces there, then reinstall from longhandlit.com/write/ and paste them in.

## The writing app

Longhand runs in Chrome or Microsoft Edge on a Mac or Windows PC and works without the internet once installed. Every piece is saved as you type in the browser's own storage (IndexedDB) on that computer, and nothing is ever sent to a server. **Export** is the only way writing leaves the app: Word (.docx), PDF (through the print window's "Save as PDF"), Markdown (.md) or plain text (.txt).

To install it, open `…/write/` in Chrome and click the install icon at the right end of the address bar. In Edge, open the **⋯** menu and choose **Apps → Install this site as an app**.

Keys (on Windows, use Ctrl where these say ⌘, and Shift for ⇧):

- ⌘S confirms the piece is saved. Longhand saves on its own as you type.
- ⇧⌘S opens the Export menu.
- ⌘I and ⌘B for italics and bold. Type `#` and a space at the start of a line for a heading.
- Esc brings the buttons back while you're writing.

The app's files are in `write/`: `index.html` (page and styling), `app.js` (editor and saving), `export.js` (Word, Markdown and plain-text exports), `sw.js` (offline support; bump `VERSION` there whenever an app file changes), and `manifest.webmanifest` with `icons/` (what Chrome needs to install it).
