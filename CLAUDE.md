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
- **Polytopes** (`polytopes/`): interactive shape references, starting with `polyhedra/`. Every fact
  is worked out from the shapes themselves, never from a cache, and like the lessons the pages never
  mention a specific cache. The tools share one notepad in `localStorage` (key `aft.polytopes.notes`).
- **Never rename or move a published tool's folder.** Cache pages link to these addresses, and
  GitHub doesn't redirect Pages URLs.

## How changes land
Work on a branch and open a pull request. Aegis reviews and merges, and Pages republishes `main`
within a few minutes.

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
