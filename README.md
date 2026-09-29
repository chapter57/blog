# Longhand

A quiet place to write, and a little company while you do: a free writing app, an almanac for writers, and an occasional essay on craft.

The site is built by GitHub Pages from this project. Changes go live a minute or two after they reach the `gh-pages` branch. Readers write to longhandlit@gmail.com (set as `email` in `_config.yml`).

## Posting to the Almanac and adding essays (the easy way)

The site is set up for **Pages CMS**, a free editor that works like a blog dashboard. Its settings are in `.pages.yml`.

1. Go to [app.pagescms.org](https://app.pagescms.org) and sign in with GitHub.
2. The first time, allow Pages CMS access to the `chapter57/longhand` project when GitHub asks, then open the project and choose the `gh-pages` branch.
3. Choose **Almanac** or **Essays** in the sidebar, click **Add an entry**, and fill in the boxes:
   - **Almanac:** Title, Date, Kind of post (Prompt, Note, Open calls or News), an optional Summary, and the post itself.
   - **Essays:** Title, Description, Author, Date, and the essay itself.
4. Click **Save**. The post is published to the site a minute or two later.

The newest **Prompt** is featured on the front page with a "Write it in Longhand" button, and the four latest other posts are listed beside it. Every post also appears on the Almanac page (`/almanac/`), grouped by month, and in the feed at `/almanac/feed.xml`. Images added in the editor are stored in `assets/images/`.

## What's where

- `index.html`: the front page, with the app, the Almanac, the essays and "Write to us"
- `_posts/`: Almanac posts, one file each, named by date and title
- `almanac/index.html`: the Almanac page, listing every post by month
- `_essays/`: one file per craft essay
- `_layouts/`, `_includes/`, `assets/site.css`: the page design; the drawings (pen, moon phases, postmark, envelope, ink rule) are in `_includes/ill-*.html`
- `.pages.yml`: the Pages CMS editing screens
- `_config.yml`: site settings
- `fonts/`: Literata and IBM Plex Mono, both under the SIL Open Font License (see `fonts/OFL.txt`)
- `write/`: the Longhand writing app
- `sw.js`: retires the offline copy that older installs of the app kept at the site's main address

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
