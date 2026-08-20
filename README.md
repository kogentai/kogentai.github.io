# kogent.ai

Landing page for Kogent: solutions for knowledge work in the agentic engineering era, enabling the dark factory pattern by supplying the context agents need to run lights-out.

Hosted on GitHub Pages with the custom domain `kogent.ai` (see `CNAME`). Plain static HTML with no build step. Edit the page and push to `main` to deploy.

## Pages

- `index.html` — the landing page. The only page on this site.

## The Trust Center is not here

The Trust Center used to live at `/trust/`, linked from the landing footer. It
is now **product documentation**, not marketing: it ships inside the app's Doc
Center, in the Kogent monorepo at
`apps/kogent/docs/user/trust-center.md` (`user` persona).

That move is deliberate, not a tidy-up. The Trust Center makes specific,
falsifiable claims about the product's security posture, and in the monorepo
each claim is pinned to the source files that back it — the
`docs:check` gate fails when a pinned file changes and the prose has not been
re-read. A hand-maintained copy on a build-less static site cannot be held to
that, and a second copy would drift out of step with the first. So: **do not
re-add a Trust Center page to this repo.** Send people to the app docs instead.

A separate marketing-side statement of posture still exists in the monorepo at
`apps/website/src/app/trust/page.jsx` (the majordomo.md site); it is unaffected
by this and remains marketing copy.
