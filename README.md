# JatriSeba

JatriSeba — a Bangladesh transport and travel information platform built to
help users explore transport options and destinations.

Live demo: https://jatriseba.pages.dev

> **Demo, not a booking service.** All schedules, fares, ratings, bookings,
> chats and accounts in this project are sample data, simulated in the
> browser. No real ticket is booked, no payment is processed, and there is
> no backend or database.

## Overview

JatriSeba is a single-page prototype. A traveller can search for a bus or
train, compare options, pick seats on a visual seat map, plan a
multi-transport journey, and explore places to visit across Bangladesh's
divisions — all from one page, in English and Bangla.

## Problem statement

Transport information in Bangladesh is spread across operators, stations
and timetables. A traveller planning a trip often has to check several
places to compare a bus with a train, estimate a fare, or work out a
transfer in Dhaka. JatriSeba puts a small, searchable sample of that
information in one place, so the comparison — not just a single result —
is easy to see.

## Key features

Verified in the code in this repository and in the live demo:

- **Top search** — search by place name, or by origin and destination,
  in English and Bangla (for example, Dhaka to Chattogram)
- **Intercity buses** — 16 sample trips, with operator, bus type,
  departure time and maximum fare, and a visual seat map with an
  in-session double-booking guard
- **Dhaka local buses** — 6 sample routes, with ordered stops, transfers
  and a trip planner by stop
- **Search by place** — type a city, boarding/dropping point or Dhaka stop
  and see the sample buses and local routes that pass through it
- **Train Seba** — 16 sample trains, with schedule, journey time,
  intermediate stations, route filter and name/station search, and sample
  ticket prices for Shovan Chair, Snigdha and AC Berth classes
- **Best Suggestion** — compares options with a transparent score
  breakdown: 35% fare, 30% journey time, 25% rating, 10% transfers,
  with balanced, lowest-fare, shortest-journey and highest-rating modes
- **Ratings** — 5-star ratings that update the average in the browser
  session only, one rating per service per session, with edit/report
- **Journey planner** — multi-transport plans (walk, bus, transfer, walk)
  on a Leaflet map, with routes drawn as clearly labelled approximate lines
- **Explore Bangladesh** — 8 division cards, each opening a hero/intro
  plus 5 attraction cards (40 attractions in total), with attraction
  detail views, search and type filters (historical, beach, hills, forest,
  river, religious, family)
- **Simulated chat, accounts and dashboards** — messages, registration,
  login, password change/recovery, editable profile and a unique QR code
  per account, all simulated in the browser session only, nothing sent
  to a server, and chat is not end-to-end encrypted
- **About and Founder section** — what the platform does, how scoring
  and ratings work, a report-incorrect-information form, and a Founder
  & Chairman section (Meer Abdullah Al Bayzid, student of Uttara
  University, CSE)

## Screenshots / demo preview

No screenshots are included in this repository, because no genuine
screenshot was captured for this version. Use the live demo instead —
it is the same interface, with full photos:

https://jatriseba.pages.dev

## Technology stack

- HTML, CSS and JavaScript — no build step, no framework, no backend
- Leaflet 1.9.4 (via CDN) for maps
- Google Fonts: Hind Siliguri and Archivo (via CDN)
- No npm dependencies, no database, no server code

## Project structure

```
jatriseba/
├── index.html              # Markup only (entry point, links CSS/JS below)
├── css/
│   └── style.css           # All page styling
├── js/
│   └── app.js              # Sample datasets first, then rendering + logic
├── README.md               # This file
└── assets/
    └── placeholder.svg     # Placeholder used in this repo copy (see below)
```

The sample datasets sit at the top of `js/app.js`, then the rendering
and booking logic follows. `index.html` loads them in this order:
Leaflet (CDN), a small Leaflet shim, QRCode (CDN), then `js/app.js`.
That order matters — do not move `app.js` before Leaflet.

### Note on this repo copy (image-light, split files)

This repo copy is split into `index.html`, `css/style.css` and
`js/app.js` (about 304 KB in total), so it uploads cleanly to GitHub
and is easier to read than the old single-file version. The old
single-file `index.html` was replaced by this split version — the
entry point is still `index.html`, it just loads CSS/JS from separate
files now. 60 division, attraction and category photos are replaced
with `assets/placeholder.svg`. The founder photo is kept as-is.

The full version, with all photos inlined, is about 16 MB and is the
version live at https://jatriseba.pages.dev. The code, search, seat map,
trains, map, chat and About sections are otherwise the same.

## Installation and setup

There is nothing to install.

```bash
git clone https://github.com/Bayzid-12/jatriseba.git
cd jatriseba
```

No Node, npm, database or environment variables are required.

## Running locally

Open the file directly in a browser:

```bash
# Option 1: open the file
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Or serve the folder over HTTP (useful if a browser blocks local files):

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Internet is needed only for the Leaflet map tiles and Google Fonts.
If the map tiles cannot load, the ordered stop lists and journey steps
are still shown on the page.

## Configuration

There is no configuration. There are no API keys, environment variables,
backend URLs or merchant credentials in this project. Do not add any —
this demo is designed to run without them.

## Current limitations

Stated honestly, so a reviewer does not mistake this prototype for a
production ticketing platform:

- **Sample data only** — bus and train schedules, fares, availability
  and ratings are not live, not verified against operators or Bangladesh
  Railway, and will go out of date.
- **No backend, no database** — bookings, ratings, chats and accounts
  exist only in the browser session and are lost on refresh.
- **No real payments** — any payment flow is a sandbox/demo flow, and
  tickets stay marked "Pending verification" in the demo.
- **No real authentication** — registration and login are simulated;
  no password is ever stored or sent anywhere.
- **Map routes are approximate** — lines connect known endpoints and
  stops only; a bus's real road path is not shown, and there is no live
  GPS tracking.
- **Known content issues** — the Bike category banner still uses the
  Lalbagh Fort photo instead of a motorcycle/ride photo, and the
  homepage hero reuses the Chattogram division card photo.
- **Repo photos** — in this GitHub copy, most photos are placeholders
  (see "Note on this repo copy" above); the live demo has the full photos.
- **Train coverage** — only 16 sample trains, not the full Bangladesh
  Railway timetable.

## Future improvements

In a sensible order, not all at once:

1. Move photos out of the single file into `assets/` as separate files,
   and split the CSS and JavaScript out of `index.html`.
2. Fix the Bike banner photo and give the homepage hero its own photo.
3. Replace the sample datasets with a real, sourced API — and label
   the source and update date for every schedule and fare.
4. Add a real backend and database only if real accounts or bookings
   are ever intended, with proper authentication and payment handling.
5. Add a sitemap and Search Console verification for the live site,
   after deciding whether the final address is `jatriseba.pages.dev`
   or a custom domain.

## Contributing

This is a student demo project. If you spot wrong sample data, open an
issue describing which service, schedule or fare looks wrong and what
the correct information should be, with a source if you have one.
Pull requests that fix a documented limitation, improve accessibility
or improve documentation are welcome; please keep changes small and
do not add a backend, framework or dependency without discussing it first.

## License

No license file has been added yet, so no license is claimed here.
Adding a license (for example, MIT) is a recommended next step, but it
needs the repository owner's explicit choice — it has not been added
in this update.
