# Longhand

A quiet place to write, read, and talk about both: a free writing app, a small literary journal, and a book club.

The site is built by GitHub Pages from this project. Changes go live a minute or two after they reach the `gh-pages` branch.

## What's where

- `index.html`: the front page
- `journal/`: the journal page and the submission guidelines (`journal/submit.md`)
- `book-club/`: the book club page
- `_journal/`: one file per published journal piece
- `_data/issues.yml`: the journal's issues, with deadlines and notes
- `_data/books.yml`: the book club's books, reading schedules and questions
- `_config.yml`: site settings, including the email, newsletter and discussion links
- `_layouts/`, `_includes/`, `assets/site.css`: the page design
- `fonts/`: Literata and IBM Plex Mono, both under the SIL Open Font License (see `fonts/OFL.txt`)
- `write/`: the Longhand writing app
- `sw.js`: retires the offline copy that older installs of the app kept at the site's main address

## Switching on email, the newsletter and the discussion space

In `_config.yml`, fill in:

- `email`: where submissions and questions go
- `newsletter_username`: your username at [Buttondown](https://buttondown.com), a free newsletter service
- `discussion_url`: the invite link to your discussion space, such as a Discord server

Until one is filled in, the site says that part is coming soon.

## Adding a journal piece

1. Copy `_journal/how-to-add-a-piece.md` to a new file with a short name, like `_journal/the-orchard.md`.
2. Fill in the title, author, issue number, form (poem, fiction or essay) and bio.
3. Paste the piece below the second `---` line. For a poem, keep each line on its own line and leave an empty line between stanzas.
4. Delete the `published: false` line.

When an issue is ready, change its `status` in `_data/issues.yml` from `reading` to `published` and add its `published_on` date. To open the next issue, add a new entry at the end of that file.

## Changing the book club's book

In `_data/books.yml`, change the finished book's `status` to `past`, and add the new book with `status: current`, a short blurb, and a weekly schedule. Each week's row is highlighted on the site automatically while that week is on.

## The domain

The site lives at [longhandlit.com](https://longhandlit.com), registered at Namecheap. The `CNAME` file tells GitHub Pages to serve it there, and `url` in `_config.yml` matches.

DNS records for the website (the forum at `forum.longhandlit.com` is on Namecheap hosting and has its own record):

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
