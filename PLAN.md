# Project Plan (working title: Sans Frontières)

## Mission

Help anyone — skeptical or committed — see where their aid actually goes, and route them to the most effective way to assist allies on or near front lines. Starting with Ukraine, designed to generalize to any ally in conflict.

## Product thesis

Skepticism is the bottleneck, not generosity. v1 is a **transparency layer + call-to-action hub**, not a new donation platform.

- Show front-line need in near-real-time (what's needed, where)
- Show verified outcomes (what orgs have actually delivered — "your $50 bought X")
- Route donors to vetted channels
- Expand into direct logistics + stablecoin rails later, once trust is earned

## Target users (priority order)

1. Skeptical would-be donor — wants proof before giving (primary)
2. Committed donor — wants the highest-leverage option this week
3. Skilled volunteer (medic, vet, engineer) — wants to know where skills are needed
4. Group organizer (church, office, community) — wants to coordinate a drive

## MVP scope (v1, ~4-6 weeks part-time)

A static public website with:

- **Front-line map** — embed DeepStateMAP / ISW; don't build map infra yet
- **"What's needed now"** — curated list of verified needs by region + category
- **Vetted org directory** — 15-25 organizations, each with: category, transparency evidence, "what $X buys" example, direct donation link
- **Action hub** — routes by intent: donate / volunteer / send supplies / organize a drive
- **Email signup** — for weekly "where the money went" dispatches

**NOT in v1:** holding funds, crypto, user accounts, CMS, custom logistics.

## Data sources (all public, manual curation for v1)

- DeepStateMAP — front line (iframe)
- ISW — daily campaign assessments
- LiveUAMap — event pins
- Org-published impact/needs data: Come Back Alive, United24, Samaritan's Purse, Razom, etc.

20 well-curated entries beat 2,000 scraped ones. Build ingestion pipelines only if traction demands it.

## Tech stack (defaults — three open decisions flagged)

| Layer | Default | Notes |
|---|---|---|
| Framework | **Astro 5** | Content-first, ~zero JS by default, MDX native. **OPEN: Astro vs. Next.js** |
| Language | TypeScript | |
| Styling | **Tailwind CSS v4** | **OPEN: Tailwind vs. vanilla / CSS modules / Panda** |
| Content | MDX in repo | No CMS until pain demands one |
| Map (v1) | DeepStateMAP iframe | |
| Map (v2) | MapLibre GL + GeoJSON | Open-source, no Mapbox token |
| Hosting | **Vercel** | **OPEN: Vercel vs. Cloudflare Pages** |
| DNS / domain | Cloudflare Registrar | At-cost, no upsells |
| Analytics | Plausible or Umami | Skip GA |
| Email capture | Buttondown | When ready |
| Forms | Formspree or edge function | When ready |

## Legal / non-profit path

Three-step ladder, cheapest to most serious:

1. **Personal informational project** (v1). No entity, no donations. Zero legal overhead.
2. **Fiscal sponsor** (v1.5+). Partner with existing 501(c)(3) (Open Collective, Hack Club Bank, mission-aligned charity). Accept tax-deductible donations under their umbrella for ~5-10% overhead. No incorporation needed.
3. **Own 501(c)(3)** (v3, only if warranted). Form 1023-EZ ($275, ~3 months), 3+ board members, annual Form 990, state charity registrations. Worth it only with real traction.

**Stay at step 1 for v1.** Move up the ladder only when need outpaces overhead.

Until at least step 2, avoid: collecting/forwarding funds, facilitating shipments to combat zones (ITAR/EAR export controls), unverifiable effectiveness claims.

## Roadmap

- **v1 (4-6 weeks):** aggregator + map + directory + CTAs. Ship. Measure unique visitors + click-throughs.
- **v1.5 (2-3 months):** outreach to 3-5 listed orgs; offer to deepen their transparency presentation in exchange for attribution. Launch newsletter.
- **v2 (6-12 months):** crypto/stablecoin donation rail. USDC widget routing donations directly from donor wallet to org's published wallet — no custody, no money-transmitter licensing. Solves the fee + FX problem the donor brought up. (Aid For Ukraine has raised $100M+ in crypto via this pattern.)
- **v3 (12+ months):** platform mode if demand warrants. 501(c)(3), fund, procurement, audited impact reports. Different commitment.

## First-week deliverables (when we resume)

1. Settle name + buy domain + reserve social handles
2. Write `VISION.md` (one page: mission, audience, non-goals)
3. Research + list 15-20 candidate organizations (spreadsheet)
4. Scaffold Astro/Next.js on Vercel — blank site deployed at the domain
5. Build the static directory page from the spreadsheet

## Open decisions to research

1. **Astro vs. Next.js**
2. **Tailwind vs. alternatives**
3. **Vercel vs. Cloudflare Pages**
4. **Project name / brand**

---

## Status

- GitHub repo connected: `https://github.com/bijanp24/philanthropy.git`
- Local repo: `C:\Source\Philanthropy\SansFrontieres`
- v1 of repo contains: `README.md`, `PLAN.md`
- Toolchain: Node 24.11, npm 11.6, Git 2.43
