# Project: Clay Personalized Landing Pages

## What We're Building
One HTML landing page per prospect — personalized with their name, company name, and Clay messaging tailored to their role. Goal is to send each prospect a unique link to a page that feels built specifically for them, driving them to book a demo.

## Constraints & Decisions
- **Output format:** Plain HTML files — hosted on Vercel, GitHub repo for version control
- **Personalization depth:** Name + company name in copy; messaging adapted to their role/pain points. Not deeply researched — use CSV data only.
- **Design:** Clay brand — warm cream `#F7F4EF` background, dark text `#1A1816`, orange `#FF5F1F` accents, Montserrat (all pages), modern and minimal. Alternate sections use `#EDEAE3`. Footer is dark `#1A1816` for contrast.
- **Logos:** Clay logo direct from their CDN: `https://cdn.prod.website-files.com/61477f2c24a826836f969afe/6778506d788ebf16fef48551_Clay%20primary%20logo.avif`. Prospect company logo via `https://logo.svgcdn.com/logos/{slug}.svg`. Footer Clay logo uses `filter: brightness(0) invert(1)` since footer is dark.
- **Marquee logos:** Use `https://logo.svgcdn.com/logos/{slug}.svg` — confirmed working slugs: openai, anthropic, notion, intercom, airtable, hubspot, slack, salesforce, zapier. Vanta uses direct CDN: `https://cdn.prod.website-files.com/64009032676f24f376f002fc/6400ac82429afb0f7b31fa6c_vanta-logo.svg`. Clearbit (`logo.clearbit.com`) is broken — do NOT use it.
- **Frontend skill applied:** Scroll-reveal animations, staggered hero load, animated stat counters, scrolling marquee ticker, grain texture overlay, radial gradient orbs, card hover effects.
- **Hero visual:** CSS-built Clay spreadsheet mockup (not a real screenshot). White panel (`#FFFFFF`) with rounded top corners and soft shadow sitting on cream bg. Contains: macOS window bar, enrichment table (Company / Email / Phone / LinkedIn / Signal / Provider / AI Summary), 5 data rows, 3 animated floating badges (150+ providers, 90%+ coverage, Claygent AI). Max-width 1200px with 32px internal padding.
- **Font:** Montserrat (switched from Fraunces + Plus Jakarta Sans) — apply to all new pages
- **Content source:** CSV data + clay_icp.txt + clay_value_prop.txt (no external research)
- **CTA:** "Book a Demo" throughout each page
- **Build cadence:** One page at a time, user approves before moving to the next

## Source Files
| File | Purpose |
|------|---------|
| `landing-page-prospects.csv` | 5 prospects with name, title, company, email, LinkedIn |
| `clay_icp.txt` | Clay's ideal customer profile — pain points, buyer personas, signals |
| `clay_value_prop.txt` | Clay's value proposition, differentiators, stats, use cases |

## Prospects (5 total)
| # | Name | Title | Company | Status |
|---|------|-------|---------|--------|
| 1 | Sarah Mitchell | VP of Revenue Operations | Retool | ✅ Complete — `landing-pages/sarah-mitchell-retool.html` |
| 2 | Marcus Chen | Head of Growth | Linear | ✅ Complete — `landing-pages/marcus-chen-linear.html` |
| 3 | Emily Rodriguez | Director of Sales Development | Loom | ✅ Complete — `landing-pages/emily-rodriguez-loom.html` |
| 4 | James Okonkwo | GTM Engineer | Webflow | ✅ Complete — `landing-pages/james-okonkwo-webflow.html` |
| 5 | Rachel Goldstein | VP of Sales | Airtable | ✅ Complete — `landing-pages/rachel-goldstein-airtable.html` |

## Infrastructure
- **GitHub repo:** `https://github.com/jkw-gtme/clay-personalized-landing-pages`
- **Vercel project:** `clay-landing-pages` — auto-deploys on every push to `main`
- **Live base URL:** `https://clay-landing-pages-xi.vercel.app/`
- **Vercel root directory:** set to `landing-pages/`

## Output Location
All pages saved to: `landing-pages/`

## Page Structure (consistent across all pages)
1. **Fixed nav** — Clay logo (Clearbit) + "Book a Demo" pill button (orange)
2. **Hero** — animated badge (2 rows: logos on top, "Built for [Name]" below; `flex-direction: column`, `border-radius: 20px`) with Clay × [Company] logos, large Fraunces headline with name + company, subheading, dual CTAs, scroll indicator + CSS spreadsheet visual below (white panel, bigger than page bg to pop)
3. **Marquee ticker** — scrolling logo images (not text) on `--surface` background, greyscale with full-color hover
4. **Pain section** — numbered list of 4 role-specific pain points + sticky quote callout card
5. **How it works** — 4-column grid on `--surface`, numbered cards with hover orange tint
6. **Stats** — 4-cell grid on white, animated counters (3×, 80%, 150+, 5000+)
7. **Before & After compare** — 2-column: "Without Clay" (muted) vs "With Clay" (orange-tinted)
8. **CTA** — centered on cream with orange orb glow, personalized headline, demo button
9. **Footer** — dark `#1A1816`, Clay logo inverted to white, "Made with care for [Name] & the [Company] team"

## Messaging Guidance by Role
- **VP Revenue Operations (Sarah / Retool):** Stale CRM data, too many point tools, SDRs researching not selling, no-code ops ownership
- **Head of Growth (Marcus / Linear):** Experimental GTM motions, speed-to-lead, intent-based outreach, scaling outbound fast
- **Director of Sales Development (Emily / Loom):** SDR efficiency, personalization at scale, enrichment coverage for sequences
- **GTM Engineer (James / Webflow):** Technical workflows, waterfall enrichment, integrations, building without bottlenecks
- **VP of Sales (Rachel / Airtable):** Pipeline targets, coverage gaps, consolidating stack, faster outbound

## Per-Page Messaging Notes
- **Sarah / Retool (VP RevOps):** Table = "Retool — RevOps Enrichment". Pain: stale CRM, 5 tools with gaps, SDRs not selling, personalization doesn't scale.
- **Marcus / Linear (Head of Growth):** Table = "Linear — Growth Outbound · 612 rows". Badge 2 = "Real-time signals". Pain: intent signals expire, manual research kills experiment velocity, generic outreach, scaling = headcount.
- **Emily / Loom (Dir. Sales Dev):** Table = "Loom — SDR Outbound · 1,204 rows". Badge 2 = "90%+ email coverage". Columns: Company / Contact Email / Phone / Tech Stack / Buying Signal / Provider / AI Opener. Pain: 50% research time, 40–60% coverage dead ends, personalization headcount trap, slow rep ramp.

## Live Page URLs
| Prospect | Live URL |
|----------|----------|
| Sarah Mitchell | `https://clay-landing-pages-xi.vercel.app/sarah-mitchell-retool.html` |
| Marcus Chen | `https://clay-landing-pages-xi.vercel.app/marcus-chen-linear.html` |
| Emily Rodriguez | `https://clay-landing-pages-xi.vercel.app/emily-rodriguez-loom.html` |
| James Okonkwo | `https://clay-landing-pages-xi.vercel.app/james-okonkwo-webflow.html` |
| Rachel Goldstein | `https://clay-landing-pages-xi.vercel.app/rachel-goldstein-airtable.html` |

## Next Steps
- [ ] User to review all pages and request any copy/design changes
