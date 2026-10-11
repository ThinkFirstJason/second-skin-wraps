# Second Skin: Design Language

**Brand:** Second Skin Wraps, vinyl colour-change wraps, PPF and fleet graphics in Austin, TX (fictional)
**Concept:** *The print-shop proof sheet.* The site is a neutral grey proofing board with crop marks and registration targets, and the hero is a live colour proof. Pick a vinyl from the fan deck and the hero field and accents flood with that colour, around a real photo of the work being done.
**Audience:** Enthusiasts changing their car's colour, plus small businesses wrapping vans and trucks.
**Mood:** Confident, crafty, colourful but disciplined. A skilled print-and-install shop, not a tuner-culture site.

---

## 1. Core principles

1. **The accent is whatever the customer picked.** The site has no fixed brand colour. `--proof` is set live from the selected vinyl, and text on it flips light or dark by luminance (threshold around 0.35 relative luminance). Every other colour stays neutral so the vinyl stays the focus.
2. **Print-production vernacular as structure.** Crop marks on panel corners, a registration target as the logo mark, dashed plotter-cut lines for the process timeline, "proof" language and spec strips under the car.
3. **Asymmetric sheet layout.** Service panels sit on a 12-column grid at alternating 7/5 then 5/7 spans, like cut pieces nested on a print sheet.
4. **Square, flat and ruled.** No border radius except the registration target and timeline nodes. No shadows except the chip selection ring.
5. **Light single theme with ink bands.** The deck and footer are ink bands. Don't make a dark variant.

## 2. Colour tokens

| Token | Hex | Use |
|---|---|---|
| `--board` | `#E6E6E1` | Page background (neutral proofing-board grey) |
| `--sheet` | `#F3F3EF` | Panels and the estimator section |
| `--ink` | `#121212` | Text, fan-deck band, estimator result, footer |
| `--mid` | `#62625C` | Labels |
| `--body-2` | `#36362F` | Paragraphs |
| `--rule` | `#C4C4BD` | Hairlines, dashed dividers |
| `--proof` | *live* (default `#1F4E8C`) | Hero background, roll-bar fill. Set from the selected vinyl |
| `--on-proof` | `#F4F4F0` or `#121212` | Text on `--proof`, chosen by luminance |

**Vinyl palette (fan-deck chips):**
Gloss Deep Harbor Blue `#1F4E8C` · Satin Wet Asphalt `#3B3F42` · Gloss Kiln Orange `#C8461B` · Matte Creek Moss `#4B5A3A` · Gloss Bone `#E9E5DA` · Satin Plum Night `#3A1F4A` · Satin Pool Haze `#9DB7C4` · Gloss Racing Yellow `#F2C200` · Satin Gold Leaf `#8C7A3E`.
Finish is part of each colour's name (Gloss Kiln Orange, Satin Wet Asphalt, Matte Creek Moss). Codes follow the pattern `SSK-{G/S/M}{2-digit number}`.

## 3. Typography

| Role | Family | Settings |
|---|---|---|
| Display | **Bowlby One** (Google Fonts) | Weight 400 (it's already ultra-heavy). Hero 50–116px, line-height 0.88, letter-spacing −0.025em. H2 38–76px. H3 22–36px |
| Body | **Instrument Sans** | 400/500/600, 16.5px, 1.55 line-height |
| Specs / labels | **Martian Mono** | 10.5–12.5px, UPPERCASE labels with 0.06em tracking. Film lengths, codes, prices, times |

Bowlby One's chunky, sticker-like shapes suggest cut vinyl lettering. Use it only for headings and big result numbers.

## 4. Layout

- Max width 1400px. Gutter `clamp(16px, 4vw, 56px)`.
- **Header:** 72px on the board. The logo is a registration target (a circle with crosshairs) plus the wordmark in Bowlby One. Nav uses underline-on-hover. CTA is an ink block.
- **Proof hero:** full-bleed `--proof` field. Left: headline ("Change the colour. Keep the paint."), copy and an inverted button. Right: a 3:2 photo of an installer working film around a wheel arch, with crop marks and a mono spec strip underneath ("Picked: <finish + colour>" · code · "60" cast film · 7-yr outdoor").
- **Fan deck band:** an ink band directly under the hero. Left: a short hint line. Right: a row of 86×112px vinyl chips, each labelled with finish + name and code in mono. The selected chip lifts 8px with a board-coloured ring.
- Section intro: two columns, a big H2 on the left and a paragraph aligned to its bottom on the right.
- Mobile: single column. The process timeline turns vertical with the dashed cut line on the left.

## 5. Signature components

- **Crop marks:** `.crop` adds L-shaped 22px corner marks top-left and bottom-right in `currentColor` at 55% opacity, offset −12px outside the element. Use them on service panels and the hero car.
- **Service sheet:** `--sheet` panels on the 7/5/5/7 grid. Each opens with a full-bleed photo at the top of the panel (21:9 on the wide panels, 16:9 on the narrow ones), then a mono eyebrow, a display H3 and copy, and ends with a dashed rule above a mono "from $X · turnaround" row.
- **Film estimator:** radio pills with square 1.5px ink borders (filled ink when selected) for vehicle, coverage and film type. The ink result panel shows a huge "60 ft" figure and a **roll bar** filled with `--proof` against a 10% tick grid (film used out of a 100 ft roll), then mono rows for labour, days in the bay and estimate.
- **Plotter-cut process:** a horizontal 2px dashed ink line with hollow circle nodes. Five steps, each with a mono day label, display H3, copy and a mono hour estimate.
- **Job ledger:** a table of recent builds. Each film cell starts with a 38×24px colour swatch. Film used and days are in mono.
- **Care columns:** three columns, each with a 2px ink top rule and a list of `+` (do) and `−` (don't) items, with the signs in mono.

## 6. Photography

- Show the craft: installers' hands, squeegees, film being stretched around edges, finished cars in strong single colours or printed liveries.
- Each service gets its own proof: satin colour change, printed livery, film on a headlight, a hood stripe.
- Photos sit edge-to-edge inside panels with no rounding or shadow. Crop marks go on the panel, not the photo.
- Never use illustrated or SVG cars. The fan-deck chips are the only drawn colour.
- Source: Unsplash (free licence). Current files: `img/install.jpg`, `img/satin-gold.jpg`, `img/livery.jpg`, `img/ppf.jpg`, `img/stripe.jpg`.

## 7. Motion

- The single orchestrated moment is the colour flood: the hero background and button transition over 0.45s when a vinyl is picked, and the estimator's roll bar picks up the same colour.
- Chips lift on hover (4px) and when selected (8px). The roll bar animates its width (0.3s).
- All of this is disabled under reduced-motion.

## 8. Voice

- A craftsperson explaining the work: "Most bad wraps fail at the edges." "Treat it like paint, not like a sticker."
- Use real trade terms: cast vinyl, post-heat to ~200°F, knifeless tape, glassed out, door jambs, 60" roll, eco-solvent, laminate, PPF.
- Give concrete numbers wherever you can: feet of film, hours, days, warranty years.

## 9. Don'ts

- No "Fast & Furious" styling: neon underglow, smoke, carbon fibre, chrome type or angled slash shapes.
- No fixed brand accent colour. The vinyl is the accent.
- No rounded cards or soft shadows. Use print-sheet flatness.
- Don't use real vinyl manufacturers' colour names or codes.
