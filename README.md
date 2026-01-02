# Planned Planthood 🌱

En community-webbplats för urbana odlare som delar kunskap, tips och erfarenheter om växter och odling i stadsmiljö.

## Projektstruktur

```
Planned Planthood/
├── index.html          # Huvudsida
├── style.css           # Stilmall
├── README.md           # Dokumentation
└── assets/
    └── images/         # Bilder och ikoner
        ├── logo-*.svg      # Logotyper
        ├── icon-*.svg      # Ikoner
        ├── img-*.jpg       # Galleribilder
        └── plant-*.jpg     # Växtbilder
```

## HTML-struktur

Sidan är byggd med semantisk HTML5 och följer en tydlig hierarki:

### Huvudlayout
```html
<body>
  <main>
    <header>    <!-- Sidhuvud med logotyp och navigation -->
    <section>   <!-- Hero-sektion med bildgalleri -->
    <section>   <!-- Nyhetsbrev-anmälan -->
    <section>   <!-- Växtgrid med artikelkort -->
    <section>   <!-- Historik-sektion -->
    <footer>    <!-- Sidfot med kontaktinfo -->
  </main>
</body>
```

### Sektioner

| Sektion | Klass | Beskrivning |
|---------|-------|-------------|
| Header | `.site-header` | Logotyp, hamburger-meny (mobil) och huvudnavigation |
| Hero | `.hero` | Rubrik, beskrivning och 6-bilders galleri |
| Nyhetsbrev | `.nyhetsbrev` | Ikon och e-postformulär |
| Växter | `.våra-växter` | Grid med växtkort (artikel-element) |
| Historik | `.historik` | Tvåkolumnslayout med text och ikon |
| Footer | `.page-footer` | Om oss-text, kontaktinfo och meny |

### Tillgänglighet (a11y)
- `role`-attribut på semantiska element
- `aria-label` och `aria-labelledby` för skärmläsare
- Fokus-stilar med `outline` på interaktiva element

## CSS-struktur

Stilmallen är organiserad i logiska sektioner med kommentarer:

### CSS Custom Properties (`:root`)

**Typografi:**
- `--fw-*` — Font-vikter (400–900)
- `--fs-*` — Font-storlekar (0.625rem–3rem)
- `--font-base` — Typsnittsfamilj (Open Sans)

**Färger:**
- `--clr-neutral-*` — Gråskala (100=vit → 900=nästan svart)
- `--clr-green-*` — Gröna accentfärger
- `--clr-accent` — Primär accentfärg
- Tagg-färger för kategorier (flower, edible, decorative, etc.)

**Layout:**
- `--spacing-base` — Basenhet för spacing (1rem)
- `--header-height` — Höjd på sidhuvud (48px)
- `--gallery-row-height` — Höjd på gallerirader

### Huvudsektioner i CSS

1. **Reset & Base** — Box-sizing, margin-reset
2. **Document settings** — HTML-nivå
3. **Layout** — Main, header, section, footer
4. **Media reset** — Bilder, listor, länkar
5. **Typography** — Rubriker h1–h3
6. **Utility** — `.width-limit` container
7. **Header/navigation** — Logo och menystilar
8. **Hero section** — Galleri med CSS Grid
9. **Newsletter** — Formulärstilar
10. **Plants grid** — Växtartiklar och meta-pills
11. **History** — Tvåkolumnslayout
12. **Footer** — Sidfotslayout
13. **Responsive breakpoints** — Media queries

### Responsiv design

Tre breakpoints:

| Breakpoint | Max-width | Anpassningar |
|------------|-----------|--------------|
| Desktop | >1200px | Fullbredd, 6-kolumns galleri, 4-kolumns växtgrid |
| Tablet | ≤900px | 3-kolumns galleri, 3-kolumns växtgrid |
| Mobil | ≤600px | 2-kolumns galleri, 1-kolumns växtgrid, hamburger-meny |

### CSS-tekniker

- **CSS Grid** — Bildgalleri och växtgrid
- **Flexbox** — Header, navigation, layouter
- **CSS Nesting** — Modern nested syntax
- **Custom Properties** — Design tokens för färger/spacing
- **Pseudo-element** — Hamburger-ikon (`::before`, `::after`), watermark-overlay
- **Checkbox-hack** — Hamburger-meny utan JavaScript
- **Backdrop-filter** — Blur-effekt på mobilmeny

### Hamburger-meny (CSS-only)

Menyn fungerar utan JavaScript genom en input=checkbox:

```css
/* Dold checkbox */
>input.menu-toggle { display: none; }

/* Label som klickbar ikon */
>label.menu-toggle-label { /* hamburger-styling */ }

/* Visa meny när checkbox är :checked */
>input.menu-toggle:checked ~ nav.header-nav { display: flex; }
```
*Credit till **Petra Paulin** för idén om att animera "barsen" för hamburgermenyn till att utgöra korset.*

## Bilder

- **Logotyper:** `logo-green.svg`, `logo-white.svg`
- **Ikoner:** `icon-avatar.svg`, `icon-planting.svg`, `icon-phone.svg`, `icon-email.svg`, etc.
- **Galleri:** `img-1.jpg` – `img-6.jpg`
- **Växter:** `plant-01.jpg` – `plant-15.jpg`

## Webbläsarstöd

- Moderna webbläsare (Chrome, Firefox, Safari, Edge)
- CSS Nesting kräver Chrome 120+, Firefox 117+, Safari 17.2+
