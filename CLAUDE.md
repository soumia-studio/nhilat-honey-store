# AL-RAWAEE — Beauty Store · CLAUDE.md

## Project Overview

AL-RAWAEE (الروائع) is a premium multilingual beauty e-commerce store
selling international brands. Full shopping experience with cart and checkout.
Built with React.

## Design Direction

Inspired by: Rare Beauty — soft, refined, human, uncluttered.
NOT inspired by: loud maximalism, heavy gradients, busy layouts.

## Brand Identity

- Primary color (Magenta/Rose): #C0306A
- Gold accent: #B8962E
- Background: warm ivory/off-white #FAF7F4
- Text: deep charcoal #1C1C1C
- Soft neutrals for cards: #F2EDE8

## Logo

- The logo file is at: /src/assets/logo.png
- Always use it in the header/navbar — never recreate it as text
- On light backgrounds: use the colored version
- Minimum logo width: 120px, never stretch or distort

## Typography

- Arabic headings: "Tajawal" or "Cairo" (Google Fonts)
- Latin headings: "Cormorant Garamond" — elegant, editorial
- Body text: "DM Sans" — clean and readable
- Font sizes use rem, never px hardcoded

## Languages

Three languages supported: Arabic (ar), French (fr), English (en)

- Default language: Arabic (RTL)
- Use i18next for translations
- All UI strings go in /src/locales/{ar,fr,en}/translation.json
- Never hardcode display text in components

## Layout Rules

- Mobile-first always
- Max content width: 1280px, centered
- Generous white space — padding never below 24px on sections
- No more than 4 products per row on desktop, 2 on mobile
- Images are always the hero — never compress their display area

## Component Structure

/src
  /components
    /layout       → Navbar, Footer, LanguageSwitcher
    /ui           → Button, Badge, Card, Modal
    /product      → ProductCard, ProductGrid, ProductDetail
    /cart         → CartDrawer, CartItem, CartSummary
    /checkout     → CheckoutForm, OrderSummary
  /pages          → Home, Shop, ProductPage, Cart, Checkout, About
  /locales        → ar/, fr/, en/
  /assets         → logo, icons, placeholder images
  /context        → CartContext, LanguageContext
  /hooks          → useCart, useProducts

## Code Rules

- All colors via CSS variables in index.css — never hardcode hex in components
- Components must be functional with hooks only — no class components
- Props always typed with PropTypes or TypeScript interfaces
- No inline styles except for truly dynamic values
- Every image has a meaningful alt attribute

## Animation Style

- Subtle and purposeful — like Rare Beauty, not flashy
- Product cards: soft scale on hover (transform: scale(1.03))
- Page transitions: gentle fade-in
- Cart drawer: slides in from right (RTL: from left)
- No bouncing, no spinning, no aggressive motion

## Key UX Principles

- Cart is a slide-over drawer, not a separate page
- Product images: hover shows second image if available
- "Add to cart" always visible on product card
- Checkout: single page, clean form, no unnecessary steps
- RTL layout must mirror correctly — test every component in Arabic

## Session Discipline

Work one component or page at a time. Complete it fully before moving on.

At the end of each session, confirm: mobile responsive ✓, RTL correct ✓,
no hardcoded strings ✓, colors from CSS variables ✓.
