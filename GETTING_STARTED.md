# Your ISM Portfolio — Getting Started

This is your site, built on the [Astro Cactus](https://github.com/chrismwilliams/astro-theme-cactus)
theme, customized with your name, bio, ISM research, projects, and your real weekly journal.

## Update: journal posts corrected

The first version of this project had 6 journal posts I'd paraphrased from your old website — since
then you shared your actual Weekly Reports PDF, so **all 28 weeks are now in `content/posts/` using
your real, original writing**, not a rewritten version. If you're merging this into a project you
already have running locally, just replace your whole `content/posts/` folder with the one in this
zip (it also still has the 3 draft technical posts from before).

## Run it locally

You'll need [Node.js](https://nodejs.org) (v18+) installed. Then, in this folder:

```bash
npx pnpm install
npx pnpm dev
```

(If you have permission errors trying to install pnpm globally with `npm install -g pnpm`, `npx pnpm`
avoids that entirely — no global install needed.)

Open the URL it prints (usually `http://localhost:4321`) to see the site live — it hot-reloads as
you edit and save files.

## What's already done

- **Home** (`src/pages/index.astro`) — short intro with links to About, Projects, Journal
- **About** (`src/pages/about.astro`) — your bio, the ISM program description, your mentor's bio,
  education, awards, and skills
- **Projects** (`src/pages/projects.astro`) — a new page I added (not part of the original theme)
  listing ClearPath AI, OncoScan AI, CureAid AI, BloodLink AI, PDT Simulator, and the Biophotonics
  Masterclass
- **Journal** (`content/posts/`) — all 28 real weekly reports, plus 3 draft placeholders for the
  biomedical/AI technical posts you hadn't written yet

## Things to finish yourself

1. **Email address** — `src/components/SocialList.astro` has a placeholder `mailto:` link. Swap in
   your real email.
2. **Resume** — there's no resume page/link yet. Easiest option: drop a PDF in `public/` (e.g.
   `public/resume.pdf`) and link to it from About or the homepage.
3. **Draft posts** — `pdt-cancer-treatment.md`, `ai-healthcare-reach-problem.md`, and
   `oncoscan-cnn-walkthrough.md` are marked `draft: true` so they won't show up on the live site
   yet. Write the real content, then flip to `draft: false`.
4. **Photos** — your weekly reports mention photos (robotics competitions, the Texas A&M visit,
   Google Drive links). None are embedded yet — drop image files into `src/assets/` or `public/`
   and reference them in the relevant post if you want them showing up.
5. **Favicon/logo** — `public/icon.svg` is still the theme's default cactus icon. Replace it with
   your own square image if you want a personal favicon.
6. **Site URL** — `src/site.config.ts` is set to `https://manveertib.github.io/`. Update this if
   you deploy somewhere else.

## Deploying

This is a static site, so any static host works. The two easiest for a student project:

**GitHub Pages** (matches your old URL pattern)
1. Push this folder to a new GitHub repo.
2. In the repo, go to Settings → Pages → Build and deployment → Source: GitHub Actions, and pick
   the Astro workflow (or see the [Astro GitHub Pages guide](https://docs.astro.build/en/guides/deploy/github/)).

**Netlify or Vercel** (zero-config, usually easier)
1. Push to GitHub.
2. Import the repo on [netlify.com](https://netlify.com) or [vercel.com](https://vercel.com) — both
   auto-detect Astro. Build command: `pnpm build` (or `npm run build`). Output directory: `dist`.

Either way, once it's live, update `url` in `src/site.config.ts` to match.
