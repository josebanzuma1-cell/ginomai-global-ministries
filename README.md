# Ginomai Global Ministries — Website

A single-page church website for **Ginomai Global Ministries**.
"Ginomai" (γίνομαι) is Greek for *"to become"* — the theme that drives the whole design.

## Design

- **Palette** (from the church logo): deep navy `#151B4E`, royal navy `#212A6B`, brush sky-blue `#8FCDEA`, mist `#DCEEF9`, gold `#F4C63F`
- **Signature element**: the gold brush ring from the logo's "O", drawn animatedly around the word *Become* in the hero and repeated as section markers
- **Hero photo bed**: six ministry photos in `assets/hero/` crossfade on a 42s loop (7s each) with a slow left→right drift, layered *under* the navy gradient, glows and γίνομαι watermark at 46% opacity behind a navy scrim — the brand ground stays dominant. Per-slide framing is set inline with `--pos` (`object-position`); the branded banner shots are biased right so their baked-in logo text stays out of frame.
- **Leaders card** (About section): `assets/leaders.webp` is a background-masked cut-out of Ap. Kenneth & Ap. Agnes Bamuleta. It sits in the card frame with their heads breaking past the top edge — `.leaders-clip` uses `clip-path: inset(-70% 0 0 0 round 22px)` so the sides and bottom clip to the frame while the top stays open. The backdrop was keyed with a border-seeded flood fill using a *local* tolerance, guarded by two measured rules (`b−r > 2` = blue garment, `r−g > 34` = skin) that stop the fill dead at clothing and skin; backdrop `r−g` measures ~14, skin 52–75. No erosion — a soft-alpha gamma thins the rim instead, so hair survives. A morphological close/open pass then smooths the silhouette: closing fills the sawtooth notches where his shadowed forearm falls under the skin guard, opening strips flyaway hair strands that key into chunky specks. Only the largest connected component survives — the couple is one mass, so every island is an artifact. **Tolerance is 5 and must stay there:** at 6+ the fill creeps through anti-aliased edges into his dark watch dial (leaving a hole straight through the watch) and eats her fingers gripping his side. The old reason for a looser tolerance — backdrop residue around his trousers — no longer applies since the frame crops above them. The portrait also rises out of its frame on scroll — JS maps the card's viewport position to `--emerge`, disabled under reduced motion.
- **Motion**: page-load stagger, scroll-triggered reveals, parallax glows, marquee, hover micro-interactions — all disabled under `prefers-reduced-motion` (the hero holds a single still frame)
- Fully responsive (desktop → mobile with hamburger nav), no build step, no external dependencies

## Sections

Hero · About / γίνομαι word study · Sundays (first-visit guide) · Ministries · Watch (sermons) · Events · Give · Plan Your Visit (RSVP form) · Footer

## Run locally

Any static file server works. With Node installed:

```sh
npx serve .
```

Then open the printed URL (e.g. http://localhost:3000).

Or just open `index.html` directly in a browser — the site is fully self-contained.

## Customize before launch

Search `index.html` for these placeholders and replace with real details:

- Street address ("Kampala, Uganda — update with your street address")
- **Phone number** — the invented `+256 700 000 000` has been removed rather than replaced, so there is currently no phone contact on the site. Add a real one when you have it.
- Event dates
- Ginomai Radio: all four cards in the Watch &amp; Listen section link to `https://content-api.zeno.fm/s/9g7bTB`, which redirects to the station page at zeno.fm/radio/ginomai-radio. Zeno sends `X-Frame-Options: DENY`, so the station cannot be embedded in an iframe — linking out is the only option.
- Wire the "Plan your visit" form to a real backend (currently shows a confirmation message only)
- Swap hero photos by replacing `assets/hero/hero-1.jpg` … `hero-6.jpg` (~1500px wide, JPEG q60; adjust `--pos` on each `.hero-slide` to reframe)

Already real (do not re-placeholder): gathering times (Sunday 11:00 AM – 1:00 PM plus the three monthly gatherings), the email `ginomaiglobalministries5341@gmail.com`, the five social links with icons, the pastors names, the mobile money merchant codes, and the radio schedule.
