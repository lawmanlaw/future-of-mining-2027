# The Future of Mining Summit 2027 website

Static site: upload the whole folder to the web host for futureofminingbw.com. No build step.

## What's in it
- Intro: The Projects logo, sliced from the real artwork, assembles letter by letter, then yellow and navy panels lift away (once per visit).
- Hero: a scroll-driven journey from space. A dotted Earth in summit blue and gold turns to Africa, the logo's network connects city by city, then the camera drops into Botswana where every line converges on Gaborone, ending on the "Save the date". Map data: Natural Earth via world-atlas (public domain), pre-built into `assets/js/geo-data.js`.
- 2026 in numbers: the poster's figures, with a map of Africa whose network draws itself as you scroll.
- Registration: visitors design their own badge on a 3D lanyard (name, title, organisation, photo, finish, topics), review and flip it, pay by card, then download the badge with its QR code.
- Endorsement banner (Ministry of Minerals and Energy, Debswana, Morupule Coal Mine, Botswana Chamber of Mines), themes, 2026 video, passes, exhibit and sponsor, organiser, partners, gallery, FAQ, contact.

## Before launch, confirm these (all in `assets/js/config.js`)
- Event dates and countdown target (`dateLabel`, `eventStart`, `eventEnd`)
- Venue (`venueLabel` is set to the 2026 venue, Fairground Holdings, Gaborone)
- Social links
- All pass and booth prices and the early-bird deadline

## Taking real card payments
The checkout runs in `paymentMode: 'demo'`: the full flow works, but no money moves and no card details are collected.
To go live: open a merchant account with a card payment provider that supports Botswana (for example DPO Pay), add a small server endpoint (`paymentEndpoint`) that receives the order JSON (including each badge's details) and returns `{ "redirectUrl": "..." }` to the provider's secure card page, then set `paymentMode` to `'live'`. Never put provider secret keys in these files.

## Fonts
Headings and text use Apple's SF Pro through the system font, so iPhone, iPad and Mac visitors see real SF Pro. Apple's licence doesn't allow the SF Pro files to be hosted on a website, so other devices use Inter (bundled, open licence), which is designed to look very close.

## Assets
- `assets/logos/` transparent PNG logos, including the new `fom-summit-2027.png` lockup
- `assets/video/hero-loop.mp4` silent loop for the video section; `fom-2026-highlights.mp4` full reel with sound
