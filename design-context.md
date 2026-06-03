# SalarySe Mobile App — Design Context & Brand System

## About SalarySe
SalarySe is a fintech app for salaried employees in India. It offers a suite of financial products built around UPI, including the Level UP Card (a RuPay credit card on UPI, co-branded with CUB / City Union Bank, that lets users earn "Scoins" — a reward currency — through milestone completion and eligible transactions), SalarySe UPI (UPI payments with reward bonuses like the Salary Day Bonus offering 37.5% rewards), adjacent salary-linked financial products including InstaCash, QuickLoans, and Invest, and brand voucher redemption through Scoins. The app brand tagline is "life banti hai SalarySe" (roughly "life is made with SalarySe").

## Design Mood
Premium dark fintech, not light banking. Think Patek Philippe meets Robinhood, not generic Indian banking app. Mobile-first, max width 430px, dark mode native, reward-led, emotionally polished.

## Color System
Page canvas uses a layered gradient: `linear-gradient(180deg, #0a0628 0%, #050310 60%, #000 100%)` as the base, with 3-4 stacked radial gradients on top (purple at 50% 0%, gold at 80% 30%, lavender at 20% 60%).

- SalarySe Blue (primary brand color, primary CTAs): `#3d41fa`
- SalarySe Purple gradient (hero and progress cards): `#5b4ef5` → `#3a2db5` → `#1f1875`
- Scoin Gold: bright `#FFE07A` for reward emphasis text; deeper gradient `#FFC940` → `#C8881A` for coin highlights and reward amounts
- Reward Pink/Magenta (`#ff2bb8` → `#d91897`): reserved for the CUB issuer mark
- Success Green (`#5DCAA5` → `#1d9e75`): completed states and "live" pills
- 30-day Blue (`#378ADD` → `#1A5BA5`): separates the 30-day milestone section from the 7-day section
- Surfaces: translucent `rgba(255,255,255,0.04)` standard cards, `rgba(255,255,255,0.08)` hairline borders; elevated glass uses `rgba(255,255,255,0.15)` borders. All borders always 0.5px, never 1px or thicker.

## Typography
- Noto Sans (weights 300–800) for everything functional — body, titles, CTAs, badges, labels.
- Playfair Display italic (weights 400–600) for emotional headline moments — hero titles, section headers, large stat numbers, celebration copy. Never Playfair upright.
- Caveat for handwritten script accents (like the "up" wordmark on the Level UP card).
- Lowercase preferred throughout: "milestones" not "Milestones", "activate now" not "Activate Now". Capitalize only proper nouns: Level UP, Scoins, SalarySe, RuPay, CUB, UPI, BBPS.

## Geometry and Surfaces
Card radius 22px (large), 16px (medium), 14px (small), 999px (pills). Page padding 16–24px. Card internal padding 14–24px. Icon containers 46×46 or 60×60 rounded squares with 14–18px radius. Translucent cards use `backdrop-filter: blur(20px)`.

## The Scoin
Scoins are SalarySe's reward currency. The Scoin is a specific gold coin asset with the SalarySe "S" emblem etched on it — transparent PNG with crisp gold gradient and a serrated edge ring. Sizes: 14–18px inline in body text (currency-sign prefix before numbers), 22–28px in reward callouts, 44px in totals, 72–160px in hero/celebration states (with Y-axis rotation animation). Always this same asset — never emoji, generic coin icons, or recolored versions. Drop-shadow glow: `filter: drop-shadow(0 0 6-16px rgba(255, 201, 64, 0.5))` depending on size.

## Iconography
Inline SVG icons, Lucide-style outline at 24×24 viewBox, currentColor stroke at 2px. Never load icon fonts from CDN. Common icons: arrow-left, arrow-right, chevron-right, check, clock, credit-card, building-store, star, file-invoice, user-plus, users, gift, receipt, tag, info, shield, globe, bolt, sparkle, x.

## Motion and Animation
- Entry springs: `cubic-bezier(0.34, 1.4–1.56, 0.64, 1)` — the overshoot is the SalarySe motion signature.
- Smooth transitions (fades, slides, glows): `cubic-bezier(0.16, 1, 0.3, 1)`.
- Ambient pulse/breathing: 4–5s ease-in-out infinite loops.
- Shimmer sweeps every 3–4s on primary CTAs: linear gradient (transparent, rgba(255,255,255,0.25), transparent) translating across.
- Sequential cards stagger with 100ms offset on page load.
- Tap feedback: `transform: scale(0.97)` with 150ms transition.

## Atmospheric Elements
Ambient orbs: 240–320px blurred radial gradients in purple, gold, or blue, drifting with a 12–16s float loop. Film grain overlay: SVG turbulence noise at 4% opacity with `mix-blend-mode: overlay`, fixed across viewport. Page backgrounds layer 3–4 stacked radial gradients over a base linear gradient. Use `filter: drop-shadow()` rather than `box-shadow` so glow follows content shape (especially the Scoin).

## Tone and Copy
Everything lowercase except proper nouns. Short, reward-led, slightly playful but not childish. Active action-led CTAs: "activate now", "pay with Level UP", "claim Scoins" — never "Click here" or "Submit". Quantify rewards: "+3,650 Scoins to unlock", "earn up to 3,700 Scoins". Time-pressure cues: "7 days left", "live till 17 Aug" (gold for the deadline). Reward language: "Scoins waiting for you", "rewards are working for you", "up for grabs". Tagline "life banti hai ✦ SalarySe" always shows the sparkle, often as a footer.

## Layout Patterns
- Section headers: 28px Playfair italic on the left, small Noto Sans caption on the right with gold accent for dates. Sections divided by 36px top margin.
- Milestone/action cards: 60×60 icon container left, title + description middle, reward amount + chevron right. Vertically centered, min height ~124px.
- Hero progress cards: bright purple-blue gradient background, gold radial glow top-right, large italic Playfair stat numbers, master progress bar with shimmer pulse, two-column layout.
- Status pills: 999px radius, 4×10 padding, hairline border in matching color at 0.35 alpha, fill at 0.12–0.18 alpha, text in saturated color.
- Primary CTAs: full-width, 16–18px padding, 14–18px radius, SalarySe blue #3d41fa, white text, `drop-shadow 0 8px 28px rgba(61, 65, 250, 0.45)`, shimmer sweep, 8px gap between label and arrow icon.

## Surfaces Already Built (Level UP flow)
1. **Milestone Checklist Page** — scrollable: Scoin education card, progress overview, 7-day checklist (6 milestones), 30-day spend bonus, redemption rail with brand vouchers, brand footer.
2. **Reward Celebration Overlay** — 60% black + 30px blur overlay, hero coin rising via spring, green radial glow, orbit coins, sparkles, rotating task ticker (3s), Playfair italic total, bottom CTAs ("back to checklist" + "use Scoins" in SalarySe blue).
3. **Card Ready / Activation Overlay** — post-issuance modal: Level UP card visual enters with spring + Y-axis rotation then floats, purple ambient glow, floating Scoins, green "card issued" live-pill, Playfair italic headline, inline Scoin before "Scoins", reward hint pill ("up to ●3,700 Scoins waiting for you"), full-width "activate now" CTA.

## What to Avoid
No generic banking app aesthetics — no light backgrounds, no blue-and-red color blocking. No heavy paragraphs or marketing copy. No multiple competing CTAs per screen. No confetti, childish celebrations, or gamified scoreboards. No emoji as primary iconography. No icon fonts from CDN (inline SVG only). No 1px or thicker borders — always 0.5px. No uppercase paragraphs (uppercase only for tracked pill labels). No web dashboard layouts — mobile-first at 430px max width.
