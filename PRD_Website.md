# JobMatch Website — PRD

## Purpose
A bilingual (EN/JA) landing page that differentiates JobMatch from other part-time platforms and glorifies its matching + donation concepts through warm kawaii design.

## Sections

### 1. Nav
- Logo: "JobMatch 🍪"
- CTA button: "🚀 Launch App"
- EN/JA toggle (pill switch)
- Fixed top, backdrop blur

### 2. Hero (full viewport)
- Headline: "The part-time platform that actually matches."
- Sub: "Warm, bilingual, free. For every student in Japan."
- CTA: "🚀 Try JobMatch (it's free)"
- 4 role icons (🎓✈️🏪🌐) as visual anchor
- Soft lavender gradient background
- Animation: fade up on load

### 3. Three Differentiators (scroll cards)
- **Match vs Search** — "Match, don't search. We find your fit."
- **Bilingual vs JP-only** — "Built bilingual. For every student in Japan."
- **Free vs Fee** — "Fees are out. Cookies are in."
- No competitor names or price numbers mentioned
- Cards stagger in on scroll

### 4. Matching Spotlight (animated)
- Headline: "We don't just show listings. We find your fit."
- Animated score meter: counts 0→92% on scroll
- Two progress bars: Skills (80%) + Language (70%)
- Star rating visual (5 stars)
- One-liner about the algorithm (no formula)

### 5. Donation Spotlight (cookie jar)
- Headline: "Other platforms take a cut. We take cookies."
- 4 tier cards: 🍪¥1k / 🍪🍪¥2k / 🍪🍪🍪¥3k / 🎂¥5k
- Hover: lift + glow border
- Click: bounce + checkmark overlay
- Legal disclosure: "⚠️ This is NOT a fee. JobMatch is 100% free. Donations are voluntary gratitude gifts."
- Note: "Pick your gratitude level. No pressure. No obligation."

### 6. CTA + Footer
- Headline: "JobMatch is free. Always."
- Button: "🚀 Launch JobMatch"
- Footer: "© 2026 JobMatch · Built for students in Japan"
- Minimal — no PRD link, no tech stack, no feature list, no stats

## Design System

### Colors
| Role | Color | Hex |
|---|---|---|
| Primary | Soft Lavender | `#A78BFA` |
| Primary Dark | Violet | `#7C3AED` |
| Accent | Sakura Pink | `#FFB7C5` |
| Warm | Honey | `#FBBF24` |
| Surface | Warm Cream | `#FFF8F5` |
| Card | White | `#FFFFFF` |
| Text | Deep Plum | `#2D1B69` |
| Text Secondary | Muted Lavender | `#8B7AA8` |
| Success | Matcha Mint | `#A7F3D0` |

### Typography
- Headings: `'M PLUS Rounded 1c', sans-serif` (700)
- Body: `'Quicksand', sans-serif` (400/500/600)
- Google Fonts import

### Animations
| Element | Animation | Trigger |
|---|---|---|
| Hero | Fade up in place | Page load |
| 3 diff cards | Stagger fade up (100ms delay) | IntersectionObserver |
| Match score | Count 0→92, bars fill L→R, stars pulse | IntersectionObserver |
| Cookie cards | Sequential bounce in from bottom | IntersectionObserver |
| Cookie hover | Lift 4px + glow | :hover |
| Cookie click | Scale bounce + checkmark overlay | :active/click |
| CTA button | Gentle pulse | Continuous |

## Copy (all keys bilingual)

### EN
- Hero: "The part-time platform that actually matches."
- Hero sub: "Warm, bilingual, free. For every student in Japan."
- Diff 1: "Match, don't search. We find your fit."
- Diff 2: "Built bilingual. For every student in Japan."
- Diff 3: "Fees are out. Cookies are in."
- Match headline: "We don't just show listings. We find your fit."
- Donation headline: "Other platforms take a cut. We take cookies."
- Legal: "⚠️ This is NOT a fee. JobMatch is 100% free. Donations are voluntary gratitude gifts."
- CTA: "JobMatch is free. Always."

### JA
- Hero: "ちゃんとマッチするアルバイトプラットフォーム。"
- Hero sub: "あたたかくて、日英対応で、無料。日本のすべての学生へ。"
- Diff 1: "探さなくていい。見つけるから。"
- Diff 2: "最初からバイリンガル。日本のすべての学生のために。"
- Diff 3: "手数料はなし。クッキーはあり。"
- Match headline: "求人を探すんじゃない。あなたに合うバイトを見つける。"
- Donation headline: "他は手数料を取る。私たちはクッキーでいい。"
- Legal: "⚠️ これは手数料ではありません。JobMatchは完全無料です。寄付は任意の感謝の気持ちです。"
- CTA: "JobMatchは無料。いつまでも。"

## Technical Constraints
- Single `index.html` with inline `<style>` and inline `<script>`
- Google Fonts via `@import` in CSS
- IntersectionObserver for all scroll-triggered animations
- No dependencies, no build tools
- Must work from `file:///`
- No competitor names, no price numbers, no tech stack, no PRD links, no feature count
