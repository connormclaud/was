# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Wholesome Assembly System (WAS)** — a GitHub-deployable interlinked wiki documenting an engineering methodology for home meal preparation. The system treats lunch/nutrition planning as an engineering problem with constraints, modules, failure modes, and optimization loops.

The content is designed to be extended over time with new recipes, ingredients, techniques, and nutritional knowledge.

## Core Concepts

- **System constraints**: time budgets, macro targets, WHO-aligned nutritional guidelines
- **Weekly control loop**: batch cooking schedule (Sunday/Wednesday prep, Friday micro-reset, Saturday ceremonial)
- **Anchor modules**: interchangeable protein/grain base recipes
- **Flavor framework (Axis Rule)**: each assembly picks one from each axis — acid, fat, heat, fresh, crunch
- **Failure modes & mitigations**: fallback plans for missed prep, dry protein, appetite issues

## Build & Development

Jekyll site using the Just the Docs theme, deployed via GitHub Pages.

```bash
bundle3.3 install              # install dependencies (gems go to vendor/bundle)
bundle3.3 exec jekyll serve    # local preview at http://localhost:4000
bundle3.3 exec jekyll build    # build to _site/
```

Deployment is automatic via `.github/workflows/pages.yml` on push to `main`. On GitHub: Settings > Pages > Source must be set to "GitHub Actions".

## Adding Content

Each page is a markdown file in the repo root with YAML front matter:

```yaml
---
title: Page Title
layout: default
nav_order: 7
---
```

- `nav_order` controls sidebar position (lower = higher in nav)
- Link between pages with `[text]({% link filename.md %})`
- Link to anchors with `[text]({% link filename.md %}#heading-slug)`

## Content Conventions

- Treat meal prep concepts with engineering rigor: constraints, modules, control loops, failure modes
- Nutritional claims should reference WHO guidelines or established science
- Ingredients use German retail names (Rewe, ja!) since the author shops in Germany
- Temperatures in Celsius, weights in grams/kilograms
