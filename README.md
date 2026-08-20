# kogent.ai

Landing page for Kogent: solutions for knowledge work in the agentic engineering era, enabling the dark factory pattern by supplying the context agents need to run lights-out.

Hosted on GitHub Pages with the custom domain `kogent.ai` (see `CNAME`). Plain static HTML with no build step. Edit the page and push to `main` to deploy.

## Pages

- `index.html` — the landing page.
- `trust/index.html` — the Trust Center at `/trust/`, linked from the landing footer.

The two pages **duplicate** their chrome (design tokens, header, footer, lights
toggle) rather than sharing a stylesheet, because there is no build step and
`index.html` is the live landing page — factoring out a shared `site.css` would
mean a risky refactor of it for a second page's benefit. If you change a design
token in one, change it in the other; `trust/index.html` says so at the top of
its `<style>` block.

The Trust Center makes specific claims about the product's security posture.
Those claims are mirrored in the Kogent monorepo at
`apps/website/src/app/trust/page.jsx` — keep the two in step, and do not
describe a capability as shipped before it is.
