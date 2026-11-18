# Econ 380 Tools

Student-facing interactive tools for ECON 380, Intermediate Price Theory 1.

Published at **https://emilycleslie.github.io/econ-380-tools/**

Built to match [econ-of-crime-tools](https://github.com/emilycleslie/econ-of-crime-tools) —
same palette, same type, same layout — so the two sites read as one voice.

## What's here

```
index.html                    landing page, lists the tools
assets/style.css              the shared house style
math-proficiency/index.html   the five exams, and how they work
math-proficiency/1/index.html Math Proficiency 1 — exponents, logs, simplifying expressions
math-proficiency/2/index.html Math Proficiency 2 — derivatives and critical points
math-proficiency/3/index.html Math Proficiency 3 — partial derivatives
math-proficiency/4/index.html Math Proficiency 4 — total differentials and total derivatives
math-proficiency/5/index.html Math Proficiency 5 — solving the optimization system
allocation/index.html         Allocation mechanisms — who gets the apartments under a price ceiling (L19)
```

All five modules are built and linked. Adding a new tool means a new folder off the root and
a card on `index.html`.

## Student URLs

| Page | URL |
|---|---|
| All tools | `https://emilycleslie.github.io/econ-380-tools/` |
| Math Proficiency index | `https://emilycleslie.github.io/econ-380-tools/math-proficiency/` |
| Math Proficiency 1 | `https://emilycleslie.github.io/econ-380-tools/math-proficiency/1/` |
| Math Proficiency 2 | `https://emilycleslie.github.io/econ-380-tools/math-proficiency/2/` |
| Math Proficiency 3 | `https://emilycleslie.github.io/econ-380-tools/math-proficiency/3/` |
| Math Proficiency 4 | `https://emilycleslie.github.io/econ-380-tools/math-proficiency/4/` |
| Math Proficiency 5 | `https://emilycleslie.github.io/econ-380-tools/math-proficiency/5/` |
| Allocation mechanisms | `https://emilycleslie.github.io/econ-380-tools/allocation/` |

**The Math Proficiency 1 URL is what goes in the Learning Suite exam instructions.** It won't work
until the repo exists and Pages is switched on.

## Publishing it the first time

Two steps: make an empty repo on GitHub, then push this folder into it.

**1. On github.com**, click *New repository*. Name it `econ-380-tools`, make it **Public**,
and do **not** tick "Add a README" — this folder already has one, and a pre-made file makes
the first push more complicated. Click *Create repository*.

**2. In Terminal**, run these one at a time. The first moves Terminal into this folder —
`cd` means "change directory", and the quotes are needed because the path has spaces:

```bash
cd path/to/econ-380-tools
```

```bash
git init -b main
```

That makes this folder a git repository, with the main branch named `main`. Nothing leaves
your computer yet.

```bash
git add . && git commit -m "Econ 380 tools: Math Proficiency 1"
```

`git add .` stages every file here; `git commit` saves that snapshot with a message. Still
local.

```bash
git remote add origin https://github.com/emilycleslie/econ-380-tools.git
```

Points this folder at the repo you just made. Still nothing sent.

```bash
git push -u origin main
```

**This one uploads.** Everything in this folder becomes publicly visible on github.com.

**3. Turn on Pages.** In the repo on github.com: *Settings* → *Pages* → under "Build and
deployment", set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**,
then *Save*. Give it a minute or two, then load the Math Proficiency 1 URL above.

## Updating it later

After the first time, three commands:

```bash
cd path/to/econ-380-tools
```

```bash
git add . && git commit -m "what changed"
```

```bash
git push
```

The live site updates within a minute or so.

## ⚠️ This repo is public

Everything committed here is visible to anyone. This folder holds student-facing pages only.

The question banks, answer keys and exam files live outside this repository and must stay
there — they list the correct answer to every question students are about to be examined on.

## Editing the pages

Each page is one self-contained HTML file with no build step and no dependencies — open it in
a text editor, save, refresh. The math is plain HTML (`<sup>` for exponents, a small `.frac`
class for fractions), so there's no MathJax or KaTeX to load and nothing to break offline.

To preview before pushing, run this from the folder and open http://127.0.0.1:8740 —

```bash
python3 -m http.server 8740
```

Press Control-C in Terminal to stop it.

## Keeping the pages and the exams in step

The five sections of Math Proficiency 1 map one-to-one onto the five Learning Suite question
pools, and the page says so ("Exam group 3"). If the pools are ever regrouped in
`Fall 2026/math_review/M1_exponents_logs/generate_bank.py`, the headings here need the same
change.
