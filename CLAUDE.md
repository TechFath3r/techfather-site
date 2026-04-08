# techfather-site — CLAUDE.md

Personal profile and blog site for Dan Starr (TechFath3r), built on the Zaggonaut Astro theme and deployed to GitHub Pages at techfather.com.

## Owner

Dan Starr. Spalding, England. Board-level device repair tech, software engineer, SaaS founder.
- Repair business: DannStarr Electronics
- SaaS product: [[RepairKeeper]]
- Homelab: Mac Mini M4 Pro, Proxmox, Syncthing

## Purpose

- Professional profile — who Dan is, what he builds
- Learning log / blog — CTF writeups, homelab experiments, AI/dev observations
- Project showcase — RepairKeeper, GarageKeeper, homelab work
- Foundation for future YouTube content (blog-first, video later)

## Stack

| Layer | Choice |
|-------|--------|
| Framework | Astro 6.x |
| Styling | Tailwind CSS 4.x (via `@tailwindcss/vite`, not Astro integration) |
| Typography | `@tailwindcss/typography` |
| Language | TypeScript |
| Linting/Formatting | Biome |
| Package manager | pnpm (enforced — do not use npm/yarn) |
| Hosting | GitHub Pages |
| Domain | techfather.com |

## Key Files

| File | Purpose |
|------|---------|
| `content/configuration.toml` | All site metadata, hero text, social links, nav labels — start here |
| `src/styles/global.css` | Colour tokens (`--color-zag-accent-*`), fonts, theme variables |
| `content/blogs/` | Blog posts as Markdown files |
| `content/projects/` | Project entries as Markdown files |
| `src/components/home/Hero.astro` | Hero section on homepage |
| `src/components/home/FeaturedArticles.astro` | Blog previews on homepage |
| `src/components/home/FeaturedProjects.astro` | Project previews on homepage |
| `src/pages/` | Astro page routes |

## Accent Colour

The theme is B&W with a configurable accent. Currently emerald green (default). To change, edit `--color-zag-accent-*` variables in `src/styles/global.css`.

## Blog Categories Planned

- **CTF / Security** — OverTheWire Bandit writeups, security learning (concepts only, no spoilers/passwords)
- **Homelab** — Proxmox, Syncthing, self-hosted services
- **AI & Dev** — Claude Code, RepairKeeper development, observations
- **Repair Tech** — Board-level repair, DannStarr Electronics

## Planned Enhancements (not yet built)

- [ ] Blog post tags and category filtering
- [ ] Reading time on blog cards
- [ ] Cover image support on blog posts
- [ ] Skills/stack section on homepage
- [ ] About page with full bio
- [ ] GitHub Pages deploy action (`.github/workflows/deploy.yml`)
- [ ] DNS config for techfather.com

## Content Guidelines

- OverTheWire / CTF posts: explain *concepts and reasoning*, never post passwords or step-by-step solutions
- Tone: direct, technical but accessible — same voice Dan uses in conversation
- Posts live in `content/blogs/YYYY-MM-DD-<slug>.md` with frontmatter

## Development

```bash
pnpm install       # install deps (first time)
pnpm dev           # start dev server
pnpm build         # production build
pnpm preview       # preview production build
```

## Deployment

Target: GitHub Pages via GitHub Actions. Deploy workflow to be added at `.github/workflows/deploy.yml`. Domain: techfather.com — DNS A/CNAME records to point at GitHub Pages once repo is created.
