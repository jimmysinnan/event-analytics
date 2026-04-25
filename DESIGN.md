# Design System: Event Analytics

## 1. Visual Theme & Atmosphere
A sunlit editorial studio that happens to contain precision data. The interface sits at the intersection of warm Mediterranean light and clinical data clarity. Terracotta accents — the color of sun-baked earth and festival posters — against a cream canvas. Typography is confident and editorial, never clinical. Data is beautiful. The atmosphere is "high-end magazine layout with numbers" — not a dashboard, not a brochure: something that makes you trust the product before reading a single word.

**Density:** 5 — balanced, breathing room respected  
**Variance:** 7 — offset asymmetric, no centered layouts above mobile  
**Motion:** 6 — fluid CSS transitions, spring physics, no theatrics

## 2. Color Palette & Roles
- **Warm Canvas** (#F9F5EE) — primary background, warmer than pure white
- **Pure Surface** (#FFFFFF) — card and modal fills
- **Charcoal Ink** (#1A1412) — primary text, warmest near-black, never pure #000
- **Warm Slate** (#6B5E4E) — secondary text, descriptions, captions
- **Whisper Border** (rgba(26,20,18,0.08)) — structural lines, card borders
- **Terracotta** (#C85C3C) — SINGLE accent: CTAs, active states, focus rings, highlight text
- **Terracotta Dark** (#A8431F) — hover/pressed states of accent
- **Terracotta Muted** (rgba(200,92,60,0.10)) — subtle backgrounds on accent cards
- **Deep Night** (#1A1412) — hero/dark section backgrounds (NOT #000)
- **Deep Surface** (#231E1B) — cards within dark sections

## 3. Typography Rules
- **Display:** Fraunces — optical-size variable, track-tight at large sizes, weight 600–700, italic for emphasis. Hierarchy through weight and color, not size alone.
- **Body:** Outfit — relaxed leading (1.65), max 65ch width, Warm Slate (#6B5E4E) for body text
- **Mono:** JetBrains Mono — numbers, KPIs, code snippets, timestamps
- **Scale:** clamp() for all headlines, never fixed px at large scales
- **Banned:** Inter, Cormorant Garamond, Georgia, Times New Roman, Palatino, Arial, system-ui for headlines

## 4. Component Stylings
- **Buttons Primary:** Terracotta fill (#C85C3C), white text, no outer glow, tactile -1px translate on :active, 10px radius
- **Buttons Ghost:** 1px Charcoal Ink border, transparent fill, transitions to terracotta on hover
- **Cards:** 20px radius, Whisper Border, diffused warm shadow (hsl(20deg 30% 15% / 0.06)), used ONLY when elevation communicates hierarchy
- **Inputs:** Label above, 1.5px border, terracotta focus ring, 12px radius, no floating labels
- **Tags/Pills:** 99px radius, small uppercase text, muted accent background
- **Loaders:** Skeletal shimmer matching exact dimensions, warm shimmer (#E8D5C0 → #F5EDE0)

## 5. Layout Principles
- CSS Grid throughout — never flexbox math with calc() percentages
- Hero: SPLIT SCREEN, left-aligned. Centered hero BANNED on desktop (variance > 4)
- Feature rows: 2-column zig-zag OR asymmetric (60/40) — 3-equal-column grid BANNED
- Max-width: 1320px centered with 5% padding
- Section vertical spacing: clamp(4rem, 8vw, 7rem)
- Mobile collapse: all multi-column → single column at 768px
- min-h-[100dvh] for full-height sections (never h-screen)

## 6. Motion & Interaction
- Spring physics: ease cubic-bezier(0.34, 1.56, 0.64, 1) for entrances
- Fade+translate for scroll reveals: opacity 0→1, translateY 20px→0
- Staggered cascade: 80ms between list items
- Perpetual micro-loops: terracotta dot pulse on CTAs, subtle float on hero illustration
- Transitions: 200ms for hovers, 400ms for reveals
- Hardware-accelerated only: transform and opacity. Never animate top/left/width/height.

## 7. Anti-Patterns (Banned)
- No emojis anywhere in the UI
- No Inter, no Cormorant Garamond, no Georgia
- No pure black (#000000) — use Charcoal Ink (#1A1412)
- No neon/outer glow shadows
- No 3-column equal card grids
- No AI copywriting: "Seamless", "Unleash", "Next-Gen", "Elevate", "Game-changing"
- No fake metrics or invented statistics
- No centered hero on desktop
- No filler text: "Scroll to explore", scroll arrows, bouncing chevrons
- No broken Unsplash links — use picsum.photos with seeds if images needed
- No `LABEL // YEAR` fake design typography
- No gradient text on large headings
- No custom cursors
