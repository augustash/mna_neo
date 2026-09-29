# MNA Neo

The Neo Alchemist components that replace the exo_alchemist components of
`augustash/mna_theme` 1.x on MNA sites. One copy serves every site that requires
this package, so a change here reaches all of them on update.

## What is here

- **Components** (`components/<name>/`, `mna_neo:<name>`): `accordion_s1`,
  `hero_s1`, `image_text_s1`, `logos_s1`, `offer_s1`, `text_s1`, `webform_s1`,
  `webform_s2`. The components drawn from a site's own theme (ash on the legacy
  side), and the header and footer, live in that site's `front` theme.
- **Utilities** (`src/css/utilities.css`, imported into the front Tailwind
  build): the legacy type scales as `mna-supertitle`, `mna-title`,
  `mna-subtitle`, `mna-description` (fluid 752px to 1920px, graded by the
  heading prop's size), `mna-ink` / `mna-title-ink` (copy colours that turn
  white on dark schemes), `mna-prose` (rich text in Foundation's rhythm),
  `mna-paragraphs` (short descriptions), and the button pair `mna-btn` /
  `mna-btn-outline`.
- **Includes** (`templates/includes/`): `links.html.twig`, the solid-then-outline
  button pair every component shares, and `vertical-padding.html.twig`, the exo
  vertical padding values as classes.

A site places a component through a `neo_component` config entity of its own;
this package ships only the components and their utilities.

## Styled to the first site

The components were rebuilt against the first site migrated (Wise Heating & Air
Conditioning), because `mna_theme` shipped no component styles: each site's
theme styled them. Colours follow the site's schemes and pallets where the
legacy theme used its theme colours, but some values are fixed as that site had
them: the button red (`#892020`), the title grey (`#373a3c`), the copy black
(`#1a1a1a`) and the lime icon colour on dark bands. The next site should compare
against its own legacy pages and move any value that differs into a token.

Site-level pieces that go with them live in the site's front theme: the section
spacing (`component-spacing`), the page's first and last section offsets, the
form look, and the faux bold the legacy copy font produced.
