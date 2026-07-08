# Instructions for Claude

## Screenshot accuracy (weekly docs refresh routine)

When refreshing product screenshots in `images/` (e.g. via the weekly docs
routine that signs into the demo environment and recaptures the standard
set):

- **Never overwrite a committed image with a broken, inaccurate, or
  low-information capture.** This includes loading skeletons, spinners,
  error/exception screens, empty states that don't match what the image is
  supposed to depict, and blank panes (e.g. map tiles that failed to load).
- If a page can't be captured in a valid, accurate state — a live bug blocks
  it, required demo data doesn't exist yet, an external dependency is
  unreachable — **leave the previously-committed image untouched** (`git
  checkout -- images/<file>.png`) rather than replace it with something
  worse. Note the gap explicitly in the PR description instead.
- Prefer no update over a misleading update. A stale-but-accurate screenshot
  is better documentation than a fresh-but-broken one.
- If a genuinely new page is broken (e.g. a newly shipped feature errors
  out), don't invent a screenshot or a doc page describing it as if it
  works — mention it exists (if the nav item is real) and flag the bug for
  engineering, but don't screenshot or document its exact behavior until
  it's verified working.
