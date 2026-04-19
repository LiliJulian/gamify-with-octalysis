# Open Source Scaffold — Design Spec
Date: 2026-04-19

## Goal

Scaffold the `gamify-with-octalysis` repo so it is ready to publish as an open source project on GitHub under the username `LiliJulian`.

## Approach

Approach B: full scaffold in a single commit, including stub example files for skills that reference them. Chosen over a single commit without stubs (broken references) and layered commits (no benefit at repo init).

## File structure

```
gamify-with-octalysis/
├── .github/
│   └── workflows/
│       └── deploy.yml                  ← GitHub Pages deploy on push to main
├── site/
│   └── index.html                      ← single-file visual reference; GitHub URL filled in
├── skills/
│   ├── octalysis-audit/
│   │   ├── SKILL.md
│   │   └── example-audit.md            ← stub (habit tracker)
│   ├── gamification-design-review/
│   │   ├── SKILL.md
│   │   └── example-review.md           ← stub (mobile onboarding flow)
│   ├── user-journey-motivation-map/
│   │   ├── SKILL.md
│   │   └── example-map.md              ← stub (meditation app)
│   └── ethical-gamification-check/
│       └── SKILL.md
├── articles/
│   └── .gitkeep
├── ATTRIBUTION.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── .gitignore
```

## Content sources

All file content is provided by the user verbatim, with two substitutions:

- `site/index.html`: "View on GitHub →" link updated from `https://github.com/` to `https://github.com/LiliJulian/gamify-with-octalysis`
- `README.md`: two occurrences of `<your-username>` replaced with `LiliJulian`

## Stub file format

Each stub (`example-audit.md`, `example-review.md`, `example-map.md`) uses this template:

```markdown
# Example [Name] — [Subject]

> This worked example is planned but not yet written.
> Want to contribute it? See [CONTRIBUTING.md](../../CONTRIBUTING.md).
```

Subject matches the description already in the corresponding `SKILL.md`.

## Deployment

GitHub Actions workflow at `.github/workflows/deploy.yml` deploys `./site` to GitHub Pages on push to `main`. No build step required — `index.html` is self-contained.

Live URL once deployed: `https://lilijulian.github.io/gamify-with-octalysis/`

## Out of scope

- Article content (placeholder directory only)
- Example file content (stubs only)
- GitHub repo creation (must be done manually by the user)
