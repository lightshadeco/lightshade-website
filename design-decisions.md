# Site Architecture & Design Decisions

> Document for [CMP-7] — last updated 2026-03-25

## Pages

| Route | Component | Description |
|-------|-----------|-------------|
| `/` | `app/page.tsx` | Home — hero, value props, featured products |
| `/about` | `app/about/page.tsx` | About — brand story, team, values |
| `/services` | `app/services/page.tsx` | Services — curtain types, design consultation, installation |
| `/products` | `app/products/page.tsx` | Products — gallery/catalog |
| `/contact` | `app/contact/page.tsx` | Contact — form, address, phone |

## Routing

- Uses **Next.js App Router** (`src/app/`)
- All pages are server components by default
- Interactive components (forms, carousels) use `"use client"` where needed

## Component Hierarchy

```
src/
├── app/
│   ├── layout.tsx           # Root layout (nav + footer)
│   ├── page.tsx             # Home
│   ├── about/
│   │   └── page.tsx
│   ├── services/
│   │   └── page.tsx
│   ├── products/
│   │   └── page.tsx
│   └── contact/
│       └── page.tsx
└── components/
    ├── layout/
    │   ├── Navbar.tsx        # Top navigation
    │   └── Footer.tsx        # Site footer
    ├── home/
    │   ├── HeroSection.tsx   # Full-width hero
    │   ├── ValueProps.tsx    # 3-column benefits
    │   └── FeaturedProducts.tsx
    ├── shared/
    │   ├── Button.tsx        # Primary/secondary/ghost variants
    │   ├── SectionHeader.tsx # Reusable heading + subtitle
    │   └── ContactForm.tsx   # Contact form (client component)
    └── products/
        └── ProductCard.tsx   # Image + title + description card
```

## Key Decisions

### Framework
- **Next.js 16 App Router** — server-first, good SEO out of the box
- Static generation (SSG) for all pages initially; add ISR when CMS is integrated

### Styling
- **Tailwind CSS 4** utility classes
- No component library (keeps bundle small, enables custom brand design)
- Color palette and typography defined in `tailwind.config.ts` once brand brief (CMP-8) is complete

### Language & i18n
- Primary: **Traditional Chinese (zh-TW)**
- `<html lang="zh-TW">` set in root layout
- i18n routing deferred until Phase 2 if needed

### Images
- Use `next/image` for all images (WebP auto-conversion, lazy loading)
- Static assets in `/public/images/`

### Forms
- Contact form: client-side validation + Next.js Server Action or API route
- Defer form backend to Phase 2 (for now, mailto fallback or Formspree)

### SEO
- `metadata` export on each page
- `sitemap.ts` + `robots.ts` added in Phase 2

## Future Considerations (Phase 2+)

- CMS integration (Sanity or Contentful) for product/service content
- i18n (English version)
- Blog / case studies section
- Online quotation form linked to curtain-quotation-system
