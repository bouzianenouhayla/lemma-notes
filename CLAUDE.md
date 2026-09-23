# Lemma — notes on AI papers

The site for **lemma-notes.com**: a library of AI research papers rewritten as
math-course notes. Published with GitHub Pages from `main` (root).

## Files

- `index.html` — the whole site: content, styles and router in one file.
- `CNAME` — the custom domain. Do not change or delete it.

## How the content works

Two lists near the top of the `<script>` block in `index.html` hold everything:

- `CHAPTERS` — the sections (§1 Evaluation, §2 Agents & tool use, …). The order
  of this array sets the § numbers, so do not reorder it once posts are live.
- `LEMMAS` — one object per post. Fields: `id` (slug used in the URL hash),
  `chapter` (a chapter `id`), `num` (position inside that chapter, so
  chapter 1 + num 2 renders as "Lemma 1.2"), `title`, `statement`, `paper`,
  `paperUrl`, `postUrl` (the LinkedIn carousel), `date`, `ink` and `body`.
- `ARCHIVE` — earlier LinkedIn posts that have no full write-up, shown as
  dashed "Earlier note" cards.
- `BODIES` — the reading page for each lemma, keyed by its `body` name. HTML
  using the classes below.

## Adding a lemma

1. Append an object to `LEMMAS` with the next `num` in its chapter.
2. Add its reading page to `BODIES` under the same key as its `body` field.
3. Commit and push. GitHub Pages redeploys within about a minute.

The table of contents, numbering, counts and search update on their own.

## House style

- A lemma's `title` is the paper's own title, verbatim. Never replace it with a
  claim or a rewritten headline. The claim goes in `statement`.

- Structure every reading page as definitions and theorems first, then proofs.
  Each proof ends with `<span class="qed" aria-label="end of proof"></span>`.
- Author's asides are purple ink: `<span class="ink">↳ …</span>`. Write them in
  first person from production experience. Never invent one — leave it out
  instead and ask.
- Highlighter classes: `.hl` yellow for labels, `.hlP` pink for titles,
  `.hlG` green for key numbers.
- Math is plain HTML in `.m` (inline) or `.mb` (display). No math library.
- Placeholders are written in square brackets, e.g. `[LINKEDIN POST URL]`.
  Never invent a URL to fill one; leave the bracket and flag it.

## Constraints

- Keep the site to one self-contained file with no build step and no external
  scripts. Only the Google Fonts stylesheet is loaded from outside.
- Keep it working at phone width, keyboard-navigable, and legible in both the
  paper and chalkboard themes.
- Show the diff and wait for approval before pushing; the site is public.
