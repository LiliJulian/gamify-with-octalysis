# Open Source Scaffold Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Scaffold the gamify-with-octalysis repo into a fully structured open source project ready to publish and deploy on GitHub Pages.

**Architecture:** Static repo — no build step, no dependencies. A single HTML file served via GitHub Pages, four Claude skill markdown files, and standard repo housekeeping files. The GitHub Actions workflow deploys `./site` on every push to `main`.

**Tech Stack:** HTML/CSS/JS (vanilla), GitHub Actions, GitHub Pages, Markdown

> **Note on TDD:** This plan creates static content files. There is no application logic to unit-test. Each task's verification step is a visual/structural check instead.

---

### Task 1: Foundation files

**Files:**
- Create: `README.md`
- Create: `LICENSE`
- Create: `ATTRIBUTION.md`
- Create: `CONTRIBUTING.md`
- Create: `.gitignore`

- [ ] **Step 1: Create README.md**

Replace `<your-username>` with `LiliJulian` in two places. Full content:

```markdown
# gamify-with-octalysis

An open, practitioner-friendly reference for the **Octalysis Gamification Framework** by [Yu-kai Chou](https://yukaichou.com). A single-page visual guide, a set of [Claude Skills](https://docs.claude.com) for applying the framework in real design work, and companion articles.

This project is an **independent educational summary**. It is not endorsed by or affiliated with Yu-kai Chou or the Octalysis Group. All framework concepts belong to Yu-kai. See [ATTRIBUTION.md](./ATTRIBUTION.md) for full credit and linking guidance.

---

## What's inside

```
gamify-with-octalysis/
├── site/                         → the static GitHub Pages site
│   └── index.html                → single-file visual reference
├── skills/                       → Claude Skills for applying Octalysis
│   ├── octalysis-audit/          → score a product across all 8 drives
│   ├── gamification-design-review/ → review a feature before shipping
│   ├── user-journey-motivation-map/ → map drives to journey phases
│   └── ethical-gamification-check/ → flag Black Hat overuse & dark patterns
├── articles/                     → Substack drafts and companion essays
├── ATTRIBUTION.md                → credit, linking, licensing notes
├── CONTRIBUTING.md               → how to suggest examples, fixes, translations
├── LICENSE                       → MIT
└── README.md
```

## Live site

Once deployed to GitHub Pages, the site will live at:

```
https://LiliJulian.github.io/gamify-with-octalysis/
```

To preview locally, any static file server works:

```bash
cd site
python3 -m http.server 8080
# open http://localhost:8080
```

No build step, no dependencies — it's a single HTML file.

## The eight Core Drives

| # | Drive | Hat | Brain |
|---|-------|-----|-------|
| CD1 | 🌟 Epic Meaning & Calling | White | Right |
| CD2 | 🏆 Development & Accomplishment | White | Left |
| CD3 | 🎨 Empowerment of Creativity & Feedback | White | Right |
| CD4 | 💎 Ownership & Possession | White | Left |
| CD5 | 👥 Social Influence & Relatedness | White | Right |
| CD6 | ⏳ Scarcity & Impatience | Black | Left |
| CD7 | 🎲 Unpredictability & Curiosity | Black | Right |
| CD8 | ⚠️ Loss & Avoidance | Black | Left |

The visual reference in `site/index.html` goes deeper on each drive with real product examples, techniques, and designer tips.

## The Skills

Four Claude Skills that turn the framework into day-to-day design tools. Each one lives in `skills/<name>/SKILL.md` and can be dropped into any Claude setup that supports skills.

- **`octalysis-audit`** — score a product 0–10 across all 8 drives, draw the resulting octagon, flag Black Hat overuse and White Hat gaps.
- **`gamification-design-review`** — review a feature or flow through the motivation lens before it ships.
- **`user-journey-motivation-map`** — map which drives should dominate at each phase: Discovery, Onboarding, Habit, Mastery, Endgame.
- **`ethical-gamification-check`** — scan for dark patterns, manufactured scarcity, and drives that will feel coercive to users.

## Articles

Plain-language explainers meant for Substack or blog syndication:

- **What is the Octalysis Framework?** — an introduction for designers and PMs.
- **White Hat vs. Black Hat gamification** — when each is appropriate.
- **Auditing a product with Octalysis** — walked-through example.

Drafts live in `articles/`.

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md). Welcome contributions:

- New real-world product examples for a Core Drive
- Corrections or clearer wording
- Translations of the site or articles
- Additional skill recipes

## License

- **Code** (HTML/CSS/JS): [MIT License](./LICENSE)
- **Content** (skill markdown, article drafts, site copy): free to reuse with attribution — see [ATTRIBUTION.md](./ATTRIBUTION.md)

All Octalysis Framework concepts, language, and structure belong to Yu-kai Chou and are used here under educational fair use with attribution. If you are Yu-kai or a representative and would like anything changed, please open an issue.

## Credits

- **Framework**: [Yu-kai Chou](https://yukaichou.com), *Actionable Gamification* (2015)
- **Deeper learning**: [Octalysis Group](https://octalysisgroup.com) — certifications, consulting, workshops
- **This reference**: an open-source community summary
```

- [ ] **Step 2: Create LICENSE**

```
MIT License

Copyright (c) 2026 gamify-with-octalysis contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

Note on framework concepts:

The Octalysis Gamification Framework — including the names of the 8 Core
Drives, the White Hat / Black Hat distinction, the Left Brain / Right Brain
distinction, and related terminology — is the intellectual work of Yu-kai Chou,
described in his book "Actionable Gamification" (2015). The MIT License above
applies only to the original code, prose, and structure created for this
repository, not to the underlying framework.

For commercial training, certification, or consulting based on Octalysis,
please contact the Octalysis Group: https://octalysisgroup.com
```

- [ ] **Step 3: Create ATTRIBUTION.md**

```markdown
# Attribution

## Framework

The **Octalysis Gamification Framework** is the original work of **Yu-kai Chou**, first published on yukaichou.com and expanded in his 2015 book *Actionable Gamification: Beyond Points, Badges, and Leaderboards*.

All concepts in this repository — including the 8 Core Drives, the names and numbering of each drive (CD1–CD8), the White Hat / Black Hat distinction, the Left Brain / Right Brain distinction, and the specific techniques associated with each drive (e.g., "Appointment Dynamics," "Epic Narrative," "Sunk Cost Pity") — belong to Yu-kai Chou.

This repository is an **unofficial, independent educational summary** intended to help designers, product managers, educators, and students learn and apply the framework. It does not replace the original book or the Octalysis Group's professional training.

## How to cite this work

If you use the visual reference, Claude Skills, or article drafts from this repo, please credit both:

1. **Yu-kai Chou** — for the framework itself.
2. **This repository** — for the specific summary, examples, or tool.

Example citation:

> Chou, Y. (2015). *Actionable Gamification: Beyond Points, Badges, and Leaderboards.* Octalysis Media. Summary reference available at github.com/LiliJulian/gamify-with-octalysis.

## Go to the source

The best way to learn Octalysis deeply is to go straight to Yu-kai's work:

- 📘 **The book**: *Actionable Gamification* — the full, definitive treatment.
- 🌐 **yukaichou.com** — blog, talks, free articles, and updates.
- 🎓 **Octalysis Group** (octalysisgroup.com) — certifications, workshops, and consulting taught by Yu-kai and his team. Recommended if you want to practice the framework professionally.

## For Yu-kai or the Octalysis Group

If you are Yu-kai Chou or an authorized representative of the Octalysis Group and would like:

- Any wording changed,
- A specific example added or removed,
- A link added or improved,
- Or this repository taken down,

please open a GitHub issue on this repo or email the maintainer. We'll respond promptly and make changes in good faith.

## License scope recap

- **The framework concepts**: © Yu-kai Chou. Used here under educational fair use with credit.
- **This repo's original code, prose, and structure**: MIT License. Reuse freely with attribution to this repo.
- **Brand names, product names, and logos referenced as examples** (Duolingo, GitHub, Minecraft, etc.): belong to their respective owners and are used for illustrative purposes only.
```

- [ ] **Step 4: Create CONTRIBUTING.md**

```markdown
# Contributing

Thanks for considering a contribution. This project is small and the bar is friendly: if you see something that could be clearer, more accurate, or more useful to designers, open an issue or a PR.

## What we welcome

- **New real-world product examples** for any of the 8 Core Drives. Tell us what the product does, which drive it activates, and which specific technique it uses.
- **Corrections and clearer wording** — especially for anything that misrepresents Yu-kai's framework or feels like oversimplification.
- **Translations** of the site, the articles, or the skill descriptions. Language isolation shouldn't block people from learning Octalysis.
- **New skill recipes** that apply the framework to specific domains (e.g. an `octalysis-for-fitness-apps` skill).
- **Screenshots, illustrations, or diagrams** — only if you own them or they're explicitly licensed for reuse.

## What we can't accept

- Reposting or rehosting substantial portions of *Actionable Gamification*. We link to the book and the Octalysis Group — we don't replace them.
- Examples that are purely speculative ("I bet Duolingo does this"). Examples should reflect actual, observable product behavior.
- Commercial marketing material for gamification consultancies. The Octalysis Group's offerings are linked from the site; other commercial links should be judged on editorial merit.

## How to contribute

**Small edits** (typos, a link, a sentence): open a PR directly.

**New examples or content**: open an issue first. Describe what you want to add and which drive it belongs to. We'll discuss before you invest too much time.

**New skills**: open an issue first. A new skill needs a clear trigger, clear inputs, clear output format, and a worked example. See any skill in `skills/` for the structure.

## Voice and style

The site and article copy should sound like a practitioner talking to another practitioner. Concrete over abstract. Specific examples over generic claims. Short paragraphs. No buzzwords. No "revolutionary," no "paradigm shift," no "leverage synergies."

The skill markdown should be functional and compact — they're tools, not essays.

## A note on attribution

Every addition must preserve credit to Yu-kai Chou. If you describe a Core Drive or technique, mention where the framework comes from at least once per file. See [ATTRIBUTION.md](./ATTRIBUTION.md).

## Code of conduct

Be kind. Disagree on ideas, not people. If someone's example is wrong, say "I don't think this example fits CD7 because…" not "you don't get it." We're all learning.
```

- [ ] **Step 5: Create .gitignore**

```
# OS
.DS_Store
Thumbs.db

# Editors
.vscode/
.idea/
*.swp
*.swo
*~

# Node (in case anyone adds tooling later)
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*

# Python (in case article scripts get added)
__pycache__/
*.pyc
.venv/
venv/

# Local previews
.cache/
dist/
.tmp/
```

- [ ] **Step 6: Verify structure**

```bash
ls -1
```

Expected output includes: `ATTRIBUTION.md`, `CONTRIBUTING.md`, `LICENSE`, `README.md`, `.gitignore`

- [ ] **Step 7: Commit**

```bash
git add README.md LICENSE ATTRIBUTION.md CONTRIBUTING.md .gitignore
git commit -m "Add repo foundation files (README, LICENSE, ATTRIBUTION, CONTRIBUTING, .gitignore)"
```

---

### Task 2: GitHub Actions workflow

**Files:**
- Create: `.github/workflows/deploy.yml`

- [ ] **Step 1: Create directory and file**

```bash
mkdir -p .github/workflows
```

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy site to GitHub Pages

on:
  push:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Setup Pages
        uses: actions/configure-pages@v4

      - name: Upload site artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./site

      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

- [ ] **Step 2: Verify**

```bash
cat .github/workflows/deploy.yml
```

Confirm `path: ./site` is present under the upload step.

- [ ] **Step 3: Commit**

```bash
git add .github/workflows/deploy.yml
git commit -m "Add GitHub Actions workflow for GitHub Pages deploy"
```

---

### Task 3: Site

**Files:**
- Create: `site/index.html`

- [ ] **Step 1: Create site directory**

```bash
mkdir -p site
```

- [ ] **Step 2: Create site/index.html**

Copy the full HTML file provided in the design spec. The one edit required is on the "View on GitHub →" anchor in the `#about` section. Find this line:

```html
<a href="https://github.com/" target="_blank" rel="noopener">View on GitHub →</a>
```

Replace with:

```html
<a href="https://github.com/LiliJulian/gamify-with-octalysis" target="_blank" rel="noopener">View on GitHub →</a>
```

- [ ] **Step 3: Verify locally**

```bash
cd site && python3 -m http.server 8080
```

Open `http://localhost:8080` in a browser. Confirm:
- The octagon renders in the hero and the explorer panel
- Clicking a segment scrolls to the correct drive card
- The "View on GitHub →" link in the About section points to `https://github.com/LiliJulian/gamify-with-octalysis`

Stop the server with `Ctrl+C`, then `cd ..`.

- [ ] **Step 4: Commit**

```bash
git add site/index.html
git commit -m "Add single-file visual reference site"
```

---

### Task 4: Skills

**Files:**
- Create: `skills/octalysis-audit/SKILL.md`
- Create: `skills/octalysis-audit/example-audit.md`
- Create: `skills/gamification-design-review/SKILL.md`
- Create: `skills/gamification-design-review/example-review.md`
- Create: `skills/user-journey-motivation-map/SKILL.md`
- Create: `skills/user-journey-motivation-map/example-map.md`
- Create: `skills/ethical-gamification-check/SKILL.md`

- [ ] **Step 1: Create skill directories**

```bash
mkdir -p skills/octalysis-audit \
         skills/gamification-design-review \
         skills/user-journey-motivation-map \
         skills/ethical-gamification-check
```

- [ ] **Step 2: Create skills/octalysis-audit/SKILL.md**

Paste the full `octalysis-audit` skill content provided in the design session verbatim (starts with `---\nname: octalysis-audit`).

- [ ] **Step 3: Create skills/octalysis-audit/example-audit.md**

```markdown
# Example Audit — Habit Tracker App

> This worked example is planned but not yet written.
> Want to contribute it? See [CONTRIBUTING.md](../../CONTRIBUTING.md).
```

- [ ] **Step 4: Create skills/gamification-design-review/SKILL.md**

Paste the full `gamification-design-review` skill content verbatim.

- [ ] **Step 5: Create skills/gamification-design-review/example-review.md**

```markdown
# Example Review — Mobile App Onboarding Flow

> This worked example is planned but not yet written.
> Want to contribute it? See [CONTRIBUTING.md](../../CONTRIBUTING.md).
```

- [ ] **Step 6: Create skills/user-journey-motivation-map/SKILL.md**

Paste the full `user-journey-motivation-map` skill content verbatim.

- [ ] **Step 7: Create skills/user-journey-motivation-map/example-map.md**

```markdown
# Example Map — Meditation App Losing Users at Week 3

> This worked example is planned but not yet written.
> Want to contribute it? See [CONTRIBUTING.md](../../CONTRIBUTING.md).
```

- [ ] **Step 8: Create skills/ethical-gamification-check/SKILL.md**

Paste the full `ethical-gamification-check` skill content verbatim.

- [ ] **Step 9: Verify structure**

```bash
find skills -type f
```

Expected output:
```
skills/octalysis-audit/SKILL.md
skills/octalysis-audit/example-audit.md
skills/gamification-design-review/SKILL.md
skills/gamification-design-review/example-review.md
skills/user-journey-motivation-map/SKILL.md
skills/user-journey-motivation-map/example-map.md
skills/ethical-gamification-check/SKILL.md
```

- [ ] **Step 10: Commit**

```bash
git add skills/
git commit -m "Add four Claude Skills for applying the Octalysis framework"
```

---

### Task 5: Articles placeholder

**Files:**
- Create: `articles/.gitkeep`

- [ ] **Step 1: Create placeholder**

```bash
mkdir -p articles
touch articles/.gitkeep
```

- [ ] **Step 2: Verify**

```bash
git status
```

Expected: `articles/.gitkeep` listed as untracked.

- [ ] **Step 3: Commit**

```bash
git add articles/.gitkeep
git commit -m "Add articles directory placeholder"
```

---

### Task 6: Final verification

- [ ] **Step 1: Check full repo structure**

```bash
find . -not -path './.git/*' -not -path './docs/*' | sort
```

Expected output:
```
.
./.github
./.github/workflows
./.github/workflows/deploy.yml
./.gitignore
./ATTRIBUTION.md
./CONTRIBUTING.md
./LICENSE
./README.md
./articles
./articles/.gitkeep
./site
./site/index.html
./skills
./skills/ethical-gamification-check
./skills/ethical-gamification-check/SKILL.md
./skills/gamification-design-review
./skills/gamification-design-review/SKILL.md
./skills/gamification-design-review/example-review.md
./skills/octalysis-audit
./skills/octalysis-audit/SKILL.md
./skills/octalysis-audit/example-audit.md
./skills/user-journey-motivation-map
./skills/user-journey-motivation-map/SKILL.md
./skills/user-journey-motivation-map/example-map.md
```

- [ ] **Step 2: Check git log**

```bash
git log --oneline
```

Expected — five commits (newest first):
```
<sha> Add articles directory placeholder
<sha> Add four Claude Skills for applying the Octalysis framework
<sha> Add single-file visual reference site
<sha> Add GitHub Actions workflow for GitHub Pages deploy
<sha> Add repo foundation files (README, LICENSE, ATTRIBUTION, CONTRIBUTING, .gitignore)
```

- [ ] **Step 3: Push to GitHub**

> The GitHub repo must exist first. Create it at github.com/new — name it `gamify-with-octalysis`, set it to Public, and do **not** initialise with a README (the repo already has commits).

```bash
git remote add origin https://github.com/LiliJulian/gamify-with-octalysis.git
git branch -M main
git push -u origin main
```

After push, go to the repo Settings → Pages → Source: GitHub Actions. The deploy workflow will run automatically on the next push, or trigger it manually from the Actions tab.
