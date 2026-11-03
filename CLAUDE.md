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
- Every tool links back to the index (`../`), and every tool is listed in `index.html` and in
  `README.md`.
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

Reviewer note when submitting: "The linked TOOL NAME page is an optional, generic helper I host
on GitHub Pages. It contains no solution information and isn't needed to solve."
