# AirVantage documentation UI library

7 October 2026 · Proposed design reference · Issue [#1133](https://github.com/andreyjv/personal-av/issues/1133)

## Open and explore

Open `dist/index.html` directly or use the private preview. No dependency installation is needed for this static library.

The homepage starts with four jobs: Activate SIMs, Order SIMs, Call the API and Register routers. Use the left navigation to explore eight complete sample pages. The right contents links locate sections. Search opens from the header or Ctrl/Cmd K; Enter opens the first result. Dark mode is a device-local preference. The mobile menu, disclosure details, tabs, changelog filters, code-copy controls and component markup controls work.

## File map

- `dist/index.html`: shared header, left navigation, article mount, right contents and search dialog.
- `dist/styles.css`: semantic tokens, two themes, layouts and component styling.
- `dist/app.js`: original specimen content, page templates and local interactions.
- `dist/favicon.svg`: simple AirVantage red geometric mark.
- `check.mjs`: syntax, routes, content IDs, contents links, copy targets and search contracts. Run from this folder with `node check.mjs`.
- `.openai/hosting.json`: private design-site identity and static asset directory. This is separate from public AirVantage documentation.

## What to borrow from Stripe

References: [Stripe documentation](https://docs.stripe.com/), [Payments guide](https://docs.stripe.com/payments), [API reference](https://docs.stripe.com/api).

Borrow the structure: job-first entry points, compact persistent navigation, an uncluttered reading column, right contents, copyable examples and nearby parameter definitions. AirVantage branding, text and source assets are original. Do not import Stripe prose, illustrations, brand colours or SDK assumptions.

## Components

The UI library includes live previews and copyable markup for actions, callouts, state badges, disclosure details, tabs, code examples, job cards and numbered steps. The site also demonstrates breadcrumbs, prerequisite lists, parameter rows, tables, search, related reading and a changelog. Snippets use the shared CSS classes; they are starter markup, not a packaged React component library. Wire their event handlers when porting them to a framework.

Tokens: red `#E53B30`; teal `#005969`; ink `#203544`; border `#E3E9EE`. Small text uses semantic foreground colours, including a darker red foreground. Spacing: 2/4/8/12/16/24/32px. Controls use 4–6px corners; cards use 8px. Body text is 14px/1.65; page titles 38px/1.18; section titles 23px/1.3. Prose has a readable line length; tables and reference examples may use the full article width. Dark mode overrides semantic tokens rather than scattering colour overrides across components.

## Integrate with the existing Docusaurus programme

This is a reviewable UI library, not a replacement implementation for the existing revamp tickets.

1. Map the shared header/sidebar/TOC to Docusaurus theme components. Preserve the site's existing router, content tree and local search integration.
2. Build the four job cards into the custom jobs homepage from #1127. Keep browse-by-product secondary.
3. Port callouts, prerequisite lists, steps and related reading into reusable MDX/React components. Use the existing corpus from #1128 and job split from #1129; do not treat these specimens as the canonical content.
4. Replace the API specimen with verified existing API HTML chapters from #1130. OpenAPI and Scalar belong to #1132. This library does not invent a live contract or execute an API request.
5. Replace changelog specimen entries with verified product release notes: date, product and breaking-change assessment. These current rows record UI-library work only.
6. Keep guides latest. Editions are context chips/categories, not duplicated guide version trees. Add API version selection only when verified versions are available.
7. Preserve AirVantage / Sierra Wireless naming until a separate rebrand decision. Keep Activate, enable and network attach distinct. Use Service plan / SIMs in operator prose; preserve API fields such as `offer` and explain the mapping once.
8. Use real content to check long titles, tables, warnings, code, mobile navigation and both themes before a production implementation is approved.

## Content and safety boundaries

The left preview note identifies guides and API content as specimens. No carrier eligibility, permissions, billing terms, exact registration procedure or production contract has been validated by this UI build. The API uses `example.invalid` and an explicit example path. It is not an AirVantage SDK. Bootstrap protection and independent state clocks are preserved from the prior design work, but the site does not operate on SIMs.

Do not edit `Mock.html`, Mock Andrey/Rupa, provisioning-tool, live `doc.airvantage.net`, DNS or production redirects as part of this library. The existing documentation remains canonical. Private preview publication changes neither the public docs nor their audience.

## Validation

Run `node check.mjs` after editing templates or navigation. It checks page titles, route/section links, unique IDs, copy targets, search, theme and accessibility hooks. It does not prove browser layout, full WCAG compliance or the accuracy of production guidance. Native server readiness and deployment status are checked separately.
