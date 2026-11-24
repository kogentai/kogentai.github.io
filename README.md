# kogent.ai

The public site for Kogent: your domain experts deliver enterprise software, and your engineers set the rules. One landing page that makes the case and asks for a demo, plus the legal and support pages the apps link to.

Hosted on GitHub Pages with the custom domain `kogent.ai` (see `CNAME`). Plain static HTML with no build step. Edit the page and push to `main` to deploy.

## Pages

- `index.html` — the landing page: headline, the 30-second film, what waiting costs, one example change, what changes, the alternatives, and "Book a demo". All its styles are inline. It works with JavaScript off.
- `privacy/`, `support/`, `account-deletion/` — legal and support pages, styled by `legal.css`. Their text is legal text; change it only with the owner.
- `media/kogent-overview.mp4` and `media/poster.jpg` — the overview film (1920×1080, 29 s, H.264, about 4.6 MB) and its poster, which is also the link-preview picture (`og:image`).

## The booking link

"Book a demo" has one home: the `href` of `<a id="booking-link">` in the demo section of `index.html`. Today it is a `mailto:` to pratul@kogent.ai with a prefilled subject and body, and the address is shown beside it as text a visitor can copy.

To move to a scheduling page, replace that one `href` with the Cal.com or Calendly URL. The header and hero buttons point at the demo section; a small script at the end of the page sends them straight to the booking URL once it is a web address. Do not add a third-party form or a tracking script.

## Copy rules

Keep the home page short (about 450 to 650 words) and written for a non-technical reader. Every product claim must hold against the shipped user documentation in the Kogent monorepo (`apps/kogent/docs/user/`). No customer names and no speed, savings or customer-count numbers.

The film uses drawings from Storyset, whose licence needs the credit "Illustrations by Storyset" in the footer. Do not use Storyset art, stock photos or other pictures as page decoration.

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
