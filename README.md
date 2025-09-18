# Tennis Courts – UI Code Challenge

Mobile‑first, two‑page app to browse tennis courts, search, view details, and leave a review.
No backend — all data is mocked in the client.

## Tech
- React + TypeScript + Vite
- Tailwind CSS
- React Router (2 routes: `/` list, `/court/:id` detail)

## Why this setup
- **Speed:** Vite for fast dev.
- **Scalable UI:** Tailwind tokens, mobile-first.
- **A11y:** Keyboard-focusable controls, visible focus states.
- **>50 Courts:** 100 deterministic mock courts generated client-side.

## Run locally
```bash
npm i
npm run dev
# or: pnpm i && pnpm dev
```

## Features
- **List page:** search (name/city/state), surface filter (all/hard/clay/grass), load-more pagination.
- **Detail page:** hero image, meta (surface/indoor/lights), average rating, user reviews.
- **Reviews:** add a rating + optional text; persisted to `localStorage`.
- **Performance:** lazy-loaded images, incremental rendering (20 per page).
- **Accessibility:** semantic labels, keyboardable controls, sufficient contrast.

## Structure
```
src/
  components/
    CourtCard.tsx
    RatingStars.tsx
    ReviewForm.tsx
    SearchBar.tsx
  pages/
    CourtsList.tsx
    CourtDetail.tsx
  lib/
    data.ts         # mock generator (100 courts)
    storage.ts      # review persistence (localStorage)
    types.ts
  index.css
  main.tsx
```

## Assumptions
- User identity is anonymous (name is free‑text).
- Average rating displays seeded mock average, overridden by user reviews when present.
- Mobile‑only scope; desktop rendering is not evaluated.

## What I’d do with more time
- Real form validation + toasts.
- Better image assets and caching.
- Virtualized list (windowing) for thousands of items.
- Map view and geolocation search.
- E2E tests (Playwright) and unit tests.

## Prompts Used
See `PROMPTS.md` in this repo for a copy of assistant prompts used to accelerate scaffolding.
