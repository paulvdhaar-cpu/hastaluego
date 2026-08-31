# Handoff: Mexico Goodbye + Birthday Party Website (design "2a")

## Overview
A single-page, **mobile-first** invitation site for a combined goodbye (3-month sabbatical) and birthday party with a Mexican taquería / street-food festival feel. It has six stacked sections: hero, rolling marquee, intro line, date & location card, photo gallery, playlist, and an RSVP footer. Design version to build is **option 2a** ("Fiesta Neon v2").

## About the Design Files
The file in this bundle (`Mexico Party.dc.html`) is a **design reference created in HTML** — a prototype showing the intended look and behavior, **not production code to copy directly**. It contains three design options (2a, 2b, 2c) plus font-comparison boxes; **only build option `#2a`**.

Your task is to **recreate the 2a design in the target codebase's environment** (React, Vue, Svelte, plain HTML/CSS, etc.) using its established patterns. If no codebase exists yet, pick the most appropriate lightweight stack — this is a small static site, so plain HTML/CSS or a single React component are both fine.

Note the prototype is built as a phone mockup inside a device bezel at a fixed 392px-wide "screen". **Ignore the bezel/notch/`.phone`/`.scr` wrappers** — those are presentation scaffolding. Build the content to fill a real responsive mobile viewport (target ~390px, scale up gracefully to tablet/desktop with a max-width container, e.g. 480px, centered).

## Fidelity
**High-fidelity (hifi).** Colors, typography, spacing, and interactions are final. Recreate pixel-accurately, then make it responsive. All exact values are in the Design Tokens section.

## Screens / Views
Single scrolling page. Sections top to bottom:

### 1. Hero
- **Purpose**: Set the mood, announce the event.
- **Layout**: Full-width, fixed height 560px, `position:relative`, `overflow:hidden`. Sits on the page-wide gradient + grain (see Background).
- **Components**:
  - **Sun motif** (top-right, 26px from right, 70px from top): 78×78px circle, `conic-gradient(from 0deg, #14251a 0 12deg, #efe6cf 12deg 24deg)`, opacity .92. A segmented pinwheel/sunburst.
  - **Eyebrow** (left 24px, top 66px): text "Despedida × Cumpleaños", Space Grotesk 700, 11px, letter-spacing .24em, uppercase, color #14251a (dark green — sits on the light upper gradient).
  - **Title H1** (left 22px, bottom 96px): "Hasta<br>Luego", Archivo Black, 96px, line-height .8, letter-spacing -.04em, uppercase, color #14251a. NOTE: deliberately low-contrast against the dark lower gradient so the letters are *barely* visible/tonal — this is an intended design element, keep it.
  - **Subline** (left 24px, right 24px, bottom 52px): "One last fiesta before I go on a 3 month sabbatical — and it's (almost) my birthday", Schibsted Grotesk 600, 16px, line-height 1.35, color #efe6cf, text-shadow 0 2px 10px rgba(0,0,0,.55).

### 2. Rolling marquee
- **Purpose**: Festive divider.
- **Layout**: Full-width yellow (#ffd23f) bar, ~11px vertical padding, `overflow:hidden; white-space:nowrap`.
- **Content**: "TACOS · MEZCAL · MÚSICA · " repeated, Archivo Black 15px, letter-spacing .04em, color #14251a.
- **Animation**: continuous horizontal scroll. Two identical spans side by side inside an inline-flex track; translateX from 0 to -50% over 20s, linear, infinite (`@keyframes mqroll { to { transform: translateX(-50%) } }`). Use `&nbsp;` or non-collapsing spacing so gaps survive.

### 3. Intro line
- **Layout**: padding 28px 24px 6px.
- **Content**: "Thirty-eight years, one big *gracias*. I'm heading off — so let's eat tacos, drink mezcal, and send it off loud." ("gracias" in italic `<em>`). Schibsted Grotesk 400, 18px, line-height 1.5, color #eae0c6, text-shadow 0 1px 6px rgba(0,0,0,.3).

### 4. Date & location card (brutalist)
- **Layout**: padding 20px 24px 8px. A cream card (#efe6cf), text #141414, `border:3px solid #141414`, square corners.
  - Top row: two equal cells split by a 3px black divider, 3px black bottom border. Cell padding 16px 18px.
    - Cell 1 label "Día" (Space Grotesk 800, 9px, letter-spacing .2em, uppercase, #c8102e) + value "14.09" (Archivo Black 34px, line-height 1, margin-top 4px).
    - Cell 2 label "Hora" (same style) + value "20:00".
  - Bottom block (padding 16px 18px): label "Lugar" (same label style but color #2f4a2e) + "LA CANTINA" (Archivo Black 26px, line-height 1.02, margin-top 5px) + "A Mexican bar · TBC · Berlin" (Space Grotesk 400, 13px, #5a5a5a).
- **Add-to-calendar button** (below card, margin-top 14px): full-width, padding 15px, background #141414, color #efe6cf, Space Grotesk 800, 15px, centered, text "＋ ADD TO CALENDAR". Downloads an `.ics` file (see Interactions).

### 5. Photo gallery ("EL ÁLBUM")
- **Layout**: padding 24px 0 8px.
- **Heading**: "EL ÁLBUM", Archivo Black 24px, letter-spacing -.02em, color #efe6cf, padded 0 24px, margin-bottom 14px.
- **Strip**: horizontal scroll (`display:flex; gap:10px; overflow-x:auto`), padded 0 24px 8px. **Max 5 photos.** Each tile: 152px wide, aspect-ratio 3/4, `border:3px solid #141414`. Placeholder fill is a diagonal hatch `repeating-linear-gradient(45deg,#e3dcc8 0 10px,#ece5d1 10px 20px)` — replace with real `<img>` (object-fit:cover). First tile has caption "last year".

### 6. Playlist
- **Layout**: margin 22px 24px, padding 22px, `border:3px solid #14251a`, background rgba(15,26,16,.35).
- **Content**: label "El Soundtrack" (Space Grotesk 700, 10px, letter-spacing .2em, uppercase, #ffd23f); title "Bangers<br>Only" (Archivo Black 28px, line-height .95, margin 8px 0 14px, #efe6cf); button "▶ PLAY THE PLAYLIST" (inline-flex, padding 11px 18px, background #ffd23f, color #14251a, Space Grotesk 800, 14px). Link the button to the real Spotify playlist URL (currently a placeholder `#`).

### 7. RSVP footer
- **Layout**: padding 20px 24px 46px.
- **Button**: full-width, padding 20px, centered, background #c8102e, color #efe6cf, Archivo Black 24px, `border:3px solid #14251a`, text "I'M IN". This is the only red accent block on the page.
- **Caption** (margin-top 10px, centered): "One tap → WhatsApp. No forms.", Space Grotesk 400, 12px, #cdd39a. Wire the button to a `wa.me` WhatsApp link (see Interactions).

## Background (applies to the whole page, behind all sections)
A single scrolling container carries the gradient and grain; all sections sit on top at `z-index:2`.
- **Gradient** (`min-height:100%`), layered top-to-bottom:
  ```
  radial-gradient(60% 34% at 55% 11%, rgba(206,17,38,.6) 0%, rgba(206,17,38,0) 60%),
  radial-gradient(42% 24% at 82% 8%, rgba(240,140,40,.5) 0%, rgba(240,140,40,0) 60%),
  radial-gradient(82% 42% at 25% 103%, rgba(16,72,44,.5) 0%, rgba(16,72,44,0) 60%),
  linear-gradient(180deg,#0c3322 0%,#134a2e 11%,#1a5836 21%,#175033 34%,#123f28 46%,#0d3121 58%,#0a2619 72%,#071a11 86%,#05120c 100%)
  ```
  i.e. a red bloom top-center, a warm-orange bloom top-right, a green glow rising from bottom-left, over a deep Mexican-flag-green → near-black vertical field.
- **Film grain**: three stacked full-bleed layers, `position:absolute; inset:0; pointer-events:none`, each an inline SVG `feTurbulence` noise data-URI:
  1. Grayscale texture, `mix-blend-mode:overlay`, opacity .4, tile 150px. Filter: fractalNoise baseFrequency 0.9, 2 octaves, desaturated, mild contrast (feFuncR/G/B slope 1.3 intercept -0.15), alpha forced to 1.
  2. Sparse **black** speckle, opacity .16, tile 170px. baseFrequency 1.0, alpha thresholded steeply (feFuncA slope 5 intercept -2.5).
  3. Sparse **white** speckle, opacity .1, tile 170px. baseFrequency 1.05, white via color matrix, alpha slope 5 intercept -2.7.
  The exact data-URIs are in the prototype (`Mexico Party.dc.html`, section `#2a`) — copy them verbatim. Grain must be **fine and subtle**, not coarse. NOTE: SVG-noise grain renders in real browsers but often looks blank in screenshot/export tools — verify in an actual browser.

## Interactions & Behavior
- **Add to calendar**: anchor with `download="fiesta.ics"` and an inline `data:text/calendar` VEVENT (SUMMARY "Hasta Luego", DTSTART 20270914T200000). Update the real date/time. For broad support consider generating a real `.ics` and, on mobile, offering Google Calendar / Apple Calendar links.
- **RSVP "I'M IN"**: should open WhatsApp — `https://wa.me/<number>?text=<prefilled RSVP>`. No form. (Currently a placeholder `#`.)
- **Playlist button**: open the real Spotify playlist (currently `#`).
- **Marquee**: infinite CSS scroll, 20s linear (see section 2).
- **Photo strip**: native horizontal touch scroll.
- No loading/error/validation states — it's a static invite.

## State Management
None required. Fully static. (If you build in React, it's a single stateless component.)

## Design Tokens
**Colors**
- Deep green field top: `#0c3322`, `#134a2e`, `#1a5836`, `#175033`, `#123f28`, `#0d3121`, `#0a2619`, `#071a11`, `#05120c` (gradient stops)
- Flag green accents / borders: `#14251a`, `#2f4a2e`, `#16724c` (rgba 16,72,44)
- Red: `#c8102e` (206,17,38) — RSVP + Día/Hora labels + top bloom
- Warm orange bloom: rgba(240,140,40,.5)
- Yellow: `#ffd23f` — marquee, playlist accents
- Cream / beige: `#efe6cf` (card, text on dark), `#eae0c6` (body copy), `#e3dcc8`/`#ece5d1` (photo placeholder hatch)
- Muted greens for captions: `#cdd39a`, `#9db09d`
- Near-black ink: `#141414`; muted gray `#5a5a5a`; placeholder text `#8a8272`

**Typography** (Google Fonts)
- Display / headings: **Archivo Black** (H1 96px, section headings 24–28px, numerals 34px)
- UI labels / eyebrows / buttons: **Space Grotesk** (700/800, 9–15px, uppercase, letter-spacing .18–.24em)
- Body / intro / hero subline: **Schibsted Grotesk** (400/600, 16–18px)
- Import: `https://fonts.googleapis.com/css2?family=Archivo+Black&family=Space+Grotesk:wght@400;500;700&family=Schibsted+Grotesk:wght@400;600&display=swap`

**Spacing**: section horizontal padding 24px; card/inner padding 16–22px; gaps 8–14px.

**Borders**: brutalist 3px solid `#141414` (light cards) / `#14251a` (on dark); dashed 1.5px `rgba(255,210,63,.55)` for the optional stamp badges (2b only). Square corners (no radius) except the circular sun motif and pill badges.

**Shadows**: text-shadow only — `0 2px 10px rgba(0,0,0,.55)` (hero subline), `0 1px 6px rgba(0,0,0,.3)` (intro).

## Assets
- **No image assets** ship with this design — the photo tiles and playlist are placeholders. Supply: up to 5 real photos (3:4 crop) and a Spotify playlist URL, a WhatsApp number, and final date/venue.
- **Icons/motifs** are pure CSS/inline SVG (sun conic-gradient; sombrero & piñata line-art SVGs appear in option 2b only — not in 2a). No icon library needed.

## Files
- `Mexico Party.dc.html` — the full prototype (multiple options + font boxes). Build **only** the section with `id="2a"` ("Fiesta Neon v2"). Options 2b (line-art sombrero/piñata stamps) and 2c (swaying piñata + ¡Dale! confetti RSVP) are alternative concepts — reference only if asked.
