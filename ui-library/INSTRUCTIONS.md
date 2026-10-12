# AirVantage documentation UI library

7 October 2026 · Proposed design reference · Issue [#1133](https://github.com/andreyjv/personal-av/issues/1133)

## Open and explore

Open `index.html` in this folder, or open `UI-library.html` at the project root. No dependency installation is needed for this static library.

The homepage starts with four jobs: Activate SIMs, Order SIMs, Call the API and Register routers. Use the left navigation to explore eight complete sample pages. The right contents links locate sections. Search opens from the header or Ctrl/Cmd K; Enter opens the first result. Dark mode is a device-local preference. The mobile menu, disclosure details, tabs, changelog filters, code-copy controls and component markup controls work.

## File map

- `index.html`: shared header, left navigation, article mount, right contents and search dialog.
- `styles.css`: semantic tokens, two themes, layouts and component styling.
- `app.js`: original specimen content, page templates and local interactions.
- `favicon.svg`: simple AirVantage red geometric mark.
- The project-root copy is `UI-library.html` plus `ui-library/`. Run `node check.mjs` from `ui-library/`.

## What to borrow from Stripe

References: [Stripe documentation](https://docs.stripe.com/), [Payments guide](https://docs.stripe.com/payments), [API reference](https://docs.stripe.com/api).

Borrow the structure: job-first entry points, compact persistent navigation, an uncluttered reading column, right contents, copyable examples and nearby parameter definitions. AirVantage branding, text and source assets are original. Do not import Stripe prose, illustrations, brand colours or SDK assumptions.

## Components

The UI library includes live previews and copyable markup for actions, callouts, state badges, disclosure details, tabs, code examples, job cards and numbered steps. The site also demonstrates breadcrumbs, prerequisite lists, parameter rows, tables, search, related reading and a changelog. Snippets use the shared CSS classes; they are starter markup, not a packaged React component library. Wire their event handlers when porting them to a framework.

Tokens: red `#E53B30`; teal `#005969`; ink `#203544`; border `#E3E9EE`. Small text uses semantic foreground colours, including a darker red foreground. Spacing: 2/4/8/12/16/24/32px. Controls use 4–6px corners; cards use 8px. Body text is 14px/1.65; page titles 38px/1.18; section titles 23px/1.3. Prose has a readable line length; tables and reference examples may use the full article width. Dark mode overrides semantic tokens rather than scattering colour overrides across components.

## Integrate with the current documentation package

This library is the interactive design reference. It does not replace the page mock or the ReadMe.com package.

- Authors write the page mock in `website/`. Activate SIMs is the first page written in full.
- Engineering pastes `Readme/` into ReadMe.com. `Readme/README.md` is the paste list.
- Map reusable patterns onto the components in `website/src/components/`. The gallery on the mock is `/docs/ui-library`.
- The specimen guides and API page stay specimens. Do not paste them over a job page.
- This file keeps its original sizes: page title 38px, section title 23px, body 14px. The mock uses display 44, title 28, body 18, small 16, caption 14, micro 12.
- On a real page, operator prose says Service plan and SIMs. The API fields stay `offer` and `offerId`. Activate, enable, and attach stay distinct. SIM statuses are Inventory, Active, Test ready, Suspended, and Retired.

## Content and safety boundaries

The left preview note identifies guides and API content as specimens. No carrier eligibility, permissions, billing terms, exact registration procedure or production contract has been validated by this UI build. The API uses `example.invalid` and an explicit example path. It is not an AirVantage SDK. Bootstrap protection and independent state clocks are preserved from the prior design work, but the site does not operate on SIMs.

Do not edit `Mock.html`, Mock Andrey/Rupa, provisioning-tool, live `doc.airvantage.net`, DNS or production redirects as part of this library. The existing documentation remains canonical. Private preview publication changes neither the public docs nor their audience.

## Validation

Run `node check.mjs` after editing templates or navigation. It checks page titles, route/section links, unique IDs, copy targets, search, theme and accessibility hooks. It does not prove browser layout, full WCAG compliance or the accuracy of production guidance. Native server readiness and deployment status are checked separately.
