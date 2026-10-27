# Jatri Sheba

Bangladesh transport and travel platform — an interactive demo, not a live booking service.

Live demo: https://jatriseba.pages.dev

## What this is

A single-page prototype for finding buses, trains, launches, bikes and private cars
across Bangladesh, with a top search, a "Best Suggestion" comparison, a journey
planner with a map, simulated chat, and an About section with a founder profile.

Everything is sample data. Schedules, fares, ratings, seat bookings, chats and
accounts are simulated in the browser only. No real ticket is booked, no payment
is processed, and nothing is sent to a server.

## Run it

No build step, no dependencies to install:

1. Open `index.html` in any modern browser.
2. That's it. Internet is only needed for the map tiles and web fonts (Leaflet, Google Fonts).

## Layout

- `index.html` — the whole demo in one file: markup, styling, sample datasets and logic.
- The datasets sit at the top of the main `<script>` block, then the rendering
  and booking logic follows. Search, seat selection and ratings all update
  in the browser session only.
