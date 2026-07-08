# Ginomai Global Ministries — Website

A single-page church website for **Ginomai Global Ministries**.
"Ginomai" (γίνομαι) is Greek for *"to become"* — the theme that drives the whole design.

## Design

- **Palette** (from the church logo): deep navy `#151B4E`, royal navy `#212A6B`, brush sky-blue `#8FCDEA`, mist `#DCEEF9`, gold `#F4C63F`
- **Signature element**: the gold brush ring from the logo's "O", drawn animatedly around the word *Become* in the hero and repeated as section markers
- **Motion**: page-load stagger, scroll-triggered reveals, parallax glows, marquee, hover micro-interactions — all disabled under `prefers-reduced-motion`
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

- Service times (`8:30 AM / 10:30 AM / 12:30 PM`)
- Street address ("Kampala, Uganda — update with your street address")
- Phone `+256 700 000 000` and email `hello@ginomaiglobal.org`
- Social handles `@GinomaiGlobal`
- Event dates and sermon titles
- Wire the "Plan your visit" form to a real backend (currently shows a confirmation message only)
