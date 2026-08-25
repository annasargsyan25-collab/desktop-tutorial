# Դարան — Online Book Rental Platform

A prototype for an online reading platform: browse a catalog, rent books
by the day, get personalized recommendations from a 3-question onboarding
quiz, leave reviews, and chat with a built-in FAQ assistant.

## Pages / flows

- **Login / Sign up** — sign up collects name, phone, email, country, and
  an optional address; returning users skip straight to the catalog.
- **Onboarding quiz** — 3 short questions (genres, era, reading pace) feed
  the "Ձեզ համար" (For you) section on the home page.
- **Home** — hero section, search, category filters (with genre icons),
  and a book grid.
- **Book detail** — description, rating, reviews (with a live comment box),
  a day-count stepper that computes the rental price, add-to-cart, and an
  instant "rent now" confirmation.
- **Cart** — empty state vs. an active checkout state once a book is added;
  confirming clears the cart and shows a success screen.
- **Profile** — pick one of 5 original illustrated avatars, edit personal
  info, toggle notifications.

## Design

Built with the `impeccable-design` / `frontend-craft` / `design-tokens` /
`accessibility-audit` skills: an apricot OKLCH accent (not the generic
"AI dark + purple" default), full light/dark theme via CSS custom
properties and a header toggle, illustrated genre-glyph book covers with
a real cover-photo fallback pulled from the Open Library Covers API,
sub-300ms motion, `aria-label`s on every icon-only button, and `<label
htmlFor>` on every form field.

## Internationalization

Full **HY / RU / EN** support via a top-menu language switcher — all UI
copy, categories, and the book catalog (titles, authors, descriptions)
are translated. Reader-submitted reviews stay in their original language,
same as most real apps don't auto-translate user-generated content.

## Assistant — Գրքիկ Գրքայան

A keyword-matched FAQ chatbot docked bottom-right. Answers common
questions (how to rent, pricing, categories, late returns, how many books
at once, changing language, etc.) in the active site language, with quick
reply suggestions. Fully client-side — no external API.

## Tech

A single self-contained `index.html`. React 18 and Babel Standalone load
from cdnjs, JSX compiles in the browser — no build step, no `npm install`.
Every book, review, and cart item lives in React state, so a refresh
resets it — there's no backend yet.

## Scope — what's intentionally not here yet

- No real backend, database, or accounts — this is a front-end-only
  prototype.
- No payment integration.
- No book uploads yet. When that ships, sharing will likely be gated to
  verified-public-domain or friends-only, to avoid distributing
  copyrighted books.
- No events feature yet.

## Running it

Open `index.html` directly in a browser — no server needed.

## Deploying

1. Push this repo to GitHub.
2. In Netlify: **Add new site → Import an existing project → GitHub** →
   pick this repo.
3. No build command or environment variables needed — Netlify serves
   `index.html` as a static site. Every push to `main` auto-deploys.
