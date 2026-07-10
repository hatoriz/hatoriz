# Corporate Identity — nathdanaik.tech
## Brand Identity Extraction

**Source:** https://nathdanaik.tech/ (fetched July 2026)
**Note on confidence:** The site's rendered CSS (exact hex values beyond the theme color, and the precise font files) could not be pulled into the build sandbox — the domain isn't reachable from this environment. Items below are marked **[confirmed]** (from the page's own metadata/content) or **[inferred]** (my reading of the visual/verbal style, to be verified against the live CSS). Where inferred, I note how to confirm.

---

## 1. Brand Essence [confirmed]

| Element | Value |
|---|---|
| **Name** | Nathdanai Kwansiripat |
| **Tagline** | Building Ecosystems That Transform |
| **Positioning line** | Executive · Coach · Entrepreneur |
| **Three brand adjectives** | Visionary · Compassionate · Transformation |
| **Values framework** | GRIT — Genuine, Rooted, Integrity, True |
| **Signature belief** | "I don't give solutions. I give people back to themselves." |
| **Thai heart-line** | ทุกคนสมควรได้อยู่ดีกินดี — everyone deserves to live well and eat well |
| **Locus** | Bangkok · GMT+7 |

**Brand architecture — "One person. Five rooms.":**
1. Modern Executive (banking)
2. Leadership Coach (for leaders quietly burning out)
3. Content Creator
4. Restaurant Entrepreneur (Som Tum Garden)
5. Real Estate Entrepreneur (community living)

---

## 2. Color [mixed]

### Confirmed
| Token | Hex | Source |
|---|---|---|
| **Base / page background** | `#FCFCFA` | `meta theme-color` — a warm, near-white off-white (paper, not stark white) |

`#FCFCFA` is the one hard value the site exposes. It sets the whole tone: **warm, calm, editorial** — an off-white "paper" ground, not a clinical `#FFFFFF`.

### Inferred palette (verify against live CSS)
Reading the editorial, grounded, "Thai soil / น้ำใจ first" tone against that warm paper base, the working palette almost certainly runs warm-neutral with an earthy accent:

| Role | Suggested token | Rationale |
|---|---|---|
| Background (paper) | `#FCFCFA` **[confirmed]** | given |
| Primary text (ink) | `#1A1A17` – `#22201B` [inferred] | warm near-black, not pure `#000` |
| Muted text | `#6B6459` [inferred] | warm grey-taupe for captions/labels |
| Hairlines / borders | `#E7E3DB` [inferred] | soft warm grey |
| Earth accent (primary) | a terracotta / clay or deep ochre [inferred] | "rooted in Thai soil" reads earthy warm |
| Deep anchor (optional) | forest / charcoal-green or deep espresso [inferred] | grounding contrast for headers/CTAs |

**How to confirm:** open the live site, inspect `:root` custom properties (the site likely defines `--bg`, `--ink`, `--accent`, etc.), or view the linked stylesheet and read the hex values directly. Replace the inferred rows above with the real tokens.

---

## 3. Typography [inferred]

The exact font files weren't retrievable, but the style signals are strong and consistent:

- **Display / headings:** a **high-contrast editorial serif** is the most likely choice — the phrases "Building Ecosystems That Transform," the numbered "(01)…(05)" room system, and the literary, essay-like voice all point to a serif with gravitas (think in the family of Canela, Freight Display, Ivar, Newsreader, or a similar editorial serif). Large, confident, generous.
- **Body / UI:** a clean, humanist **sans-serif** for readability (labels like "[ About ]", nav, running text) — likely Inter, Söhne, Neue Haas/Helvetica-grade, or similar.
- **Thai:** a harmonized Thai face is required (the site mixes Thai and English inline, e.g. ทุกคนสมควรได้อยู่ดีกินดี). Likely a modern Thai humanist sans (IBM Plex Sans Thai / Noto Sans Thai / Sarabun family) paired to the Latin sans.
- **Bracket-label motif:** section eyebrows are wrapped in brackets — `[ About ]`, `[ Values ]`, `[ Five Roles ]`, `[ The Latest ]`, `[ Connect ]`. This is a **signature typographic device** worth carrying into any sub-brand (like the dashboard/blog).

**How to confirm:** inspect `font-family` on `h1`/`body`, or check for `fonts.googleapis.com` / self-hosted `@font-face` in the CSS.

---

## 4. Voice & Tone [confirmed]

Directly observable from the copy:

- **Editorial, first-person, literary.** Full sentences, essayistic rhythm ("Twenty years inside banking, retail, and insurance taught me one thing…").
- **Warm but unsentimental.** Compassion without fluff; "Real stories, not polished PR."
- **Bilingual by nature.** Thai and English sit together as equals, not translation afterthoughts.
- **Anti-hype.** "This is a movement, not a follower count… no spam, no hard sell."
- **Access & dignity as recurring themes.** "find the people the system left without access… give them back their own dignity and agency."

**Verbal signatures to reuse:** "One person. Five rooms." · "give people back to themselves" · น้ำใจ first · "live well and eat well."

---

## 5. Layout & Motion Cues [inferred]

- **Editorial, spacious, single-column narrative** with generous whitespace on the warm paper ground.
- **Numbered index system** for the five roles — (01)–(05) — a structured, magazine-like device.
- **Bracketed section eyebrows** as navigational rhythm.
- **A marquee / running strip** ("Visionary Compassionate Transformation GRIT Bangkok" repeated) suggests a horizontal scrolling ticker element.
- Calm, restrained motion (fitting the anti-hype tone) rather than flashy animation.

---

## 6. CI Quick-Reference (for reuse in the dashboard / blog / sub-brands)

```
BRAND            Nathdanai Kwansiripat
TAGLINE          Building Ecosystems That Transform
ADJECTIVES       Visionary · Compassionate · Transformation
VALUES           GRIT — Genuine · Rooted · Integrity · True
PHILOSOPHY       "I don't give solutions. I give people back to themselves."
THAI HEART-LINE  ทุกคนสมควรได้อยู่ดีกินดี

COLOR
  bg (paper)     #FCFCFA        [confirmed]
  ink            ~#1A1A17       [inferred — verify]
  muted          ~#6B6459       [inferred — verify]
  hairline       ~#E7E3DB       [inferred — verify]
  accent (earth) terracotta/ochre [inferred — verify]

TYPE
  display        editorial serif  [inferred — verify]
  body/ui        humanist sans    [inferred — verify]
  thai           modern Thai sans, harmonized  [inferred — verify]

MOTIFS
  bracket eyebrows   [ About ] [ Values ] [ Connect ]
  numbered index     (01)…(05)
  running marquee     Visionary · Compassionate · Transformation · GRIT · Bangkok
  bilingual TH/EN inline, treated as equals
  warm paper ground, editorial whitespace, restrained motion
```

---

## 7. One Manual Step to Make This 100% Exact

I extracted everything the page exposes, but the precise non-background hexes and font names live in the site's CSS, which this environment can't reach. To lock them in, either:

- **You:** open nathdanaik.tech, right-click → Inspect → check `:root` for `--` color variables and `font-family` on `h1`/`body`, and paste them here; or
- **You:** paste the site's main `.css` file contents (or a screenshot of the homepage), and I'll replace every **[inferred]** value with the confirmed one and finalize the CI.

Everything marked **[confirmed]** above is safe to use as-is right now.
