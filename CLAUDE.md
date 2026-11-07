# adequate-footwear — standing instructions

This repository is **public**, and GitHub Pages publishes it to the open internet at
https://adequatefootwear.github.io/adequate-footwear/ from the `main` branch, root folder.
It holds Aegis's (AdequateFootwear's) **solver-facing helper tools** for its own geocaches,
the "Tools of the Trade" (TOTTs). Aegis uses **it/its** pronouns.

## The charter
Make puzzles *slightly* more accessible: take the tedium out, never hand solvers the method.

## Rules (all of them, every session)
1. **No secrets, anywhere in the repo.** No final coordinates, stage coordinates, answers,
   keywords, or expected checker values, not even hashed or obfuscated. Everything here is
   public, and everything a page runs is readable in the solver's browser. (Hashing doesn't
   help: a 2-mile circle at 0.001′ holds only ~13 million candidate points.) Checking belongs
   to Geocaching's built-in solution checker or to Certitude, never to a tool here.
2. **Optional helpers only.** Geocaching's guidelines require the information to solve a puzzle
   to be on the cache page and publicly available; a required program is generally refused.
   A tool must never be the only way to get something a solver needs.
3. **No sign-in, no tracking, no analytics**, and no collecting anything from the solver.
   Solver work may be saved in the solver's own browser (`localStorage`), nowhere else.
4. **Pages, not downloads.** Link to a tool page. If a cache page ever links a downloadable file,
   Geocaching requires this text above the link: "Alert: You are about to download a file that
   contains details needed to find this geocache."
5. **Geocaching only.** Nothing from Aegis's legal work or any client data, ever.

## How a tool is built
- One folder per tool, holding a single self-contained `index.html`: inline CSS and JS, with
  Google Fonts as the only external dependency. It must still work once loaded with no signal.
- Phone-first: most solvers open these in the field. Check at ~375 px wide, in light and dark
  mode, and with the keyboard.
- Include a built-in example made from **fictional** content, never from a real cache.
- **House look** (copy it from `read-the-sign/index.html`, since tools can't share a stylesheet):
  the forest-green-and-brass tokens on `:root` (light, dark, and `[data-theme]` blocks, plus
  `color-scheme`), the compass-needle favicon, and the green `.band` masthead with the brass
  topo-contour SVG and the "Tools of the Trade" bar linking back to `../`. Green (`--accent`) is
  for actions and highlights; red (`--error`) is only for things that went wrong; brass
  (`--brass`) is for small labels. Keep text at 4.5:1 contrast or better, and input borders at 3:1.
- Every tool links back to the index (`../`), and every tool is listed in `index.html` and in
  `README.md`.
- **Folders** group related tools: a folder holds its own `index.html` listing its tools, plus one
  subfolder per tool. The main index lists the folder as a card, not each tool inside it. A tool in
  a folder links to the folder (`../`) and to the main index (`../../`).
- **Asymmetric Cryptosystems** (`asymmetric/`): one guided worksheet per cryptosystem, named for
  the cryptosystem, never for the cache, because working out which system a puzzle uses is part of
  the puzzle. When numbers don't fit, a worksheet explains why and what that system needs, but
  never names another system. The worksheets do the hard computation (factoring, discrete logs)
  and explain each step. They share a number-theory engine, the `ntModule` function inlined in
  every worksheet (it includes a small WebAssembly routine, base64-encoded, for the discrete-log
  walk), and every worksheet also shares the `asymKit` page helpers (including the message reader).
  Keep every copy of each identical. The folder page lists worksheets alphabetically, never in
  series order, so the list doesn't map systems to caches. Not every worksheet has a cache: some are
  deliberate red herrings, which is fine, since each is a complete, working tool.
  The folder also holds four lessons, listed under “Start here”: `symmetric-and-asymmetric/`,
  `modular-arithmetic/`, `letters-to-numbers/` and `working-mod-n-squared/`. They aren't worksheets, so they don't carry
  `ntModule` or `asymKit`, and like the worksheets they never mention a specific cache.
- **Polytopes** (`polytopes/`): interactive shape references, `nets/`, `polychora/`, `polygons/` and `polyhedra/` so far,
  listed alphabetically on the folder page. Every fact is worked out from the shapes themselves, never
  from a cache, and like the lessons the pages never mention a specific cache. The tools share one
  notepad in `localStorage` (key `aft.polytopes.notes`); its markup, script and CSS are the same in
  every tool, so keep every copy identical.
- **Ruminate** (`ruminate/`) opens any file the solver gives it, on their own device; nothing is
  uploaded. It shows each file's normal views (sound and video play in the browser's own player)
  plus its text and bytes, an "Open as…" menu to try any view, and a Structure view that labels
  how a format lays out its bytes. It has no spectrogram or other audio analysis, by the owner's choice. It chooses views by the
  file's name and never guesses or names a file's type itself, and its readers are strict: a file
  that doesn't open says why, and nothing is repaired or recovered. It shares its viewer and readers
  with .bison Files, so keep every copy identical. Its built-in example is fictional.
- **Higher Powers** (`higher-powers/`): a calculator with exact and high-precision arithmetic. Its
  only short constant names are π (or `pi`), e and i; every other constant it offers goes by its full
  name (`golden_ratio`, never φ). Its mascot and decorations are secular, multicultural luck symbols,
  never religious ones.
- **Higher Powers and Constant Companion** share the number engine, the calculator and Higher Powers'
  named constants (`higherpowers.num.js`, `higherpowers.calc.js` and `higherpowers.constants.js` in
  the source repo), inlined in both pages; Constant Companion uses the constants to avoid names Higher
  Powers reserves. Keep every copy identical: after changing any of them, rebuild both pages together
  (`python3 build-lessons.py higher-powers constant-companion`).
- **Constant Companion** (`constant-companion/`): its "Send to Higher Powers" link carries the value
  only in the page address (`../higher-powers/#set=name=value`); nothing is sent anywhere, and
  Higher Powers asks before replacing a value the solver already has. A value whose digits go on
  (a mathematical constant, or a measured or cut-short one) is sent ending in `…`, so Higher Powers
  treats it as correct only to the digits sent; a complete exact value is sent plain.
- **Everything in Its Place** (`everything-in-its-place/`) stays understated: its listing says only
  "For when things need to be just so." Don't explain it further on the index, in `README.md` or on
  the page's masthead.
- **Where Are Ewe Going?** (`where-are-ewe-going/`): its encoder and decoder must match the published
  Reverse Cache Box method exactly, check digits included; never change one without the other.
- **Monkeying Around** (`monkeying-around/`) never guesses keys or ranks results: it does what the
  solver sets up, step by step, and leaves the judging to them.
- **Never rename or move a published tool's folder.** Cache pages link to these addresses, and
  GitHub doesn't redirect Pages URLs.

## Specific cache files
Everything above governs **the tools**: general helpers that never mention a specific cache, a
puzzle or its answers. The **Specific cache files** section is different and runs under its own
rules. It holds pages that carry one cache's own released files as view-only copies, so solvers
can look at them without downloading. Today that is **.bison Files** (`dot-bison-files/`).
- These pages may name their cache, talk about the puzzle, and carry the cache owner's notes
  (for example that the collection isn't needed to solve and isn't to be relied upon). The
  fictional-example rule doesn't apply: the real released files are the point.
- Rule 1 still holds: a page carries only what the cache page already makes public, never final
  or stage coordinates, answers, keywords or checker values beyond that. Rules 2 to 5 hold too.
- Show every file exactly as released, name included, and never add, guess or explain anything
  about a file beyond showing it. The viewers are strict readers: a file that doesn't open says
  why, and its Text and Bytes views still show everything.
- List them only under "Specific cache files" at the bottom of `index.html` and `README.md`,
  apart from the tools.
- They aren't generic helpers, so they have their own reviewer note (see "Linking a tool from a
  cache page").
- Never rename or move their folders either: cache pages link to them.

## How changes land
Work on a branch and open a pull request. Aegis reviews and merges, and Pages republishes `main`
within a few minutes. `main` is protected by a ruleset: nothing is pushed to it directly, and a pull
request merges only once it has an approving review. GitHub Copilot may review pull requests too
(its instructions are in `.github/copilot-instructions.md`); treat its comments like any review's:
check each one, fix what's real, and say why when something stays as it is.

## Linking a tool from a cache page
Cache pages strip JavaScript, so a cache page only links to a tool. Standard wording:

HTML:
```html
<p><strong>Optional helper:</strong> <a href="https://adequatefootwear.github.io/adequate-footwear/TOOL/">TOOL NAME</a>: SHORT DESCRIPTION. You don't need it; everything required to solve this cache is on this page and in the field.</p>
```

Plain text:
```
Optional helper: TOOL NAME, https://adequatefootwear.github.io/adequate-footwear/TOOL/ (not needed to solve; everything required is on this page and in the field).
```

For the Asymmetric series, link the folder, not a worksheet, so the link doesn't name the
cryptosystem: TOOL NAME = "Asymmetric Cryptosystems worksheets", TOOL = `asymmetric`.

Reviewer note when submitting: "The linked TOOL NAME page is an optional, generic helper I host
on GitHub Pages. It contains no solution information and isn't needed to solve."

For a page in Specific cache files, use this reviewer note instead (here for .bison Files): "The
linked .bison Files page is an optional, view-only second copy of the files this cache page
already links, which I host on GitHub Pages. It adds nothing to them and isn't needed to solve."
