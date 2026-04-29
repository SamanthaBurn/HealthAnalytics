# Introduction to Health Analytics

Course materials for *Introduction to Health Analytics*, developed by Samantha Burn at Imperial Business School.

📖 **Live course site:** [samanthaburn.github.io/HealthAnalytics](https://samanthaburn.github.io/HealthAnalytics/)

The site has rendered slide decks for every lecture and downloadable Rmd files for every exercise and tutorial. The repo contains the source for everything.

---

## Repository layout

```
lectures/        Quarto revealjs slide decks (.qmd) — one per lecture
exercises/       R Markdown exercises (.Rmd), with paired _solutions.Rmd files
tutorials/       Step-by-step .Rmd walkthroughs, organised by topic
practice_exam/   Past-style practice exam + solutions
data/            Datasets used across the course
docs/            Auto-generated rendered website (don't edit by hand)
```

---

## For students

You can either work entirely from the website or clone the repo locally.

### Option A — work from the website (no install required)

1. Visit the [course site](https://samanthaburn.github.io/HealthAnalytics/).
2. For each lecture, click "Slides" to view the deck or "Rmd" to download the exercise file.
3. Open the downloaded `.Rmd` in RStudio (see install steps below) and work through it.

### Option B — clone the whole repo

If you'd rather have everything locally:

```bash
git clone https://github.com/SamanthaBurn/HealthAnalytics.git
cd HealthAnalytics
```

Then open `exercises/exercises.Rproj` in RStudio (or any individual `.Rmd` file).

### Software you'll need

| Tool | Why | Where |
|---|---|---|
| **R** (≥ 4.0) | The language everything is written in | [r-project.org](https://www.r-project.org/) |
| **RStudio** | The IDE you'll edit and run code in | [posit.co/download/rstudio-desktop](https://posit.co/download/rstudio-desktop/) |

You don't need Quarto installed unless you want to re-render the lecture slides yourself — the rendered HTML is already on the course site.

### R packages

Most exercises auto-install the packages they need on first run via the `package.check` block at the top of each Rmd. If you'd rather pre-install everything:

```r
install.packages(c(
  "tidyverse", "broom", "modelsummary", "kableExtra", "knitr",
  "NHANES", "ipumsr", "srvyr", "survey", "fixest", "car",
  "marginaleffects", "tidymodels", "glmnet", "ggdag", "dagitty",
  "gapminder", "causaldata"
))
```

### How to use an .Rmd file

1. Open the file in RStudio (e.g. `exercises/health_analytics_05_linear_reg.Rmd`).
2. The first chunk loads packages — run it.
3. Work through each question. Write your answer in the empty `{r}` chunks. Click the green ▶︎ button to run a chunk, or place your cursor in it and press **Cmd/Ctrl + Enter**.
4. Compare with the matching `_solutions.Rmd` file when you're done (or when you're stuck).
5. Optionally **knit** the document to HTML by clicking the *Knit* button at the top — produces a self-contained HTML report of your answers.

---

## For instructors

The course is built with [Quarto](https://quarto.org/), an open-source publishing system that mixes text, code, and output.

### Software you'll need

| Tool | Why |
|---|---|
| **R** (≥ 4.0) | To run the code chunks |
| **RStudio** (2022.07 or newer) | Best editor for both `.qmd` (lectures) and `.Rmd` (exercises). Recent versions of RStudio ship with Quarto bundled, so a separate Quarto install is usually unnecessary. |
| **TinyTeX** (optional) | If you want to render exercises to PDF. Install once with `quarto install tinytex` |
| **Git** | To clone, commit, and push changes |

If you'd prefer not to use RStudio, **VS Code** with the [Quarto extension](https://marketplace.visualstudio.com/items?itemName=quarto.quarto) also works well. You can also install Quarto standalone from [quarto.org](https://quarto.org/docs/get-started/) if you want the latest version separate from whatever ships with RStudio.

A short Quarto orientation if you're new to it: [quarto.org/docs/get-started/hello/rstudio.html](https://quarto.org/docs/get-started/hello/rstudio.html). 

### How everything is organised

- **`lectures/*.qmd`** — Quarto revealjs slide decks. Each lecture is one `.qmd` that renders to an HTML slide deck. They share `lectures/burn_slides.css` for styling and use KaTeX for offline math.
- **`exercises/*.Rmd`** — Student-facing problem sets. Code chunks are mostly empty for students to fill in.
- **`exercises/*_solutions.Rmd`** — Solutions. Same structure but with the code and answers filled in.
- **`tutorials/`** — Longer step-by-step `.Rmd` walkthroughs, one per topic folder.
- **`_quarto.yml`** — Website configuration: navbar, theme, what gets rendered.
- **`index.qmd`** — Homepage of the course site.
- **`docs/`** — Auto-generated rendered output. Don't edit directly; it gets overwritten by `quarto render`.

### How to edit and re-render

**Editing slides (lectures):**

1. Open `lectures/health_analytics_NN_topic.qmd` in RStudio.
2. Edit. Slides are separated by `## Slide title`. Bullets reveal incrementally; code chunks should be wrapped in `::: {.fragment}` so they appear after the bullets.
3. Render with the RStudio "Render" button, or in terminal: `quarto render lectures/health_analytics_NN_topic.qmd`.
4. Output goes into `docs/lectures/`.

**Editing exercises:**

1. Open `exercises/health_analytics_NN_topic.Rmd`.
2. Edit. If you change the question structure, mirror the change in the `_solutions.Rmd` file too.
3. To preview: click *Knit* in RStudio (defaults to HTML).

**Rebuilding the whole site:**

```bash
quarto render
```

from the repo root rebuilds everything into `docs/`. Then commit and push:

```bash
git add -A
git commit -m "Update lectures"
git push
```

GitHub Pages auto-rebuilds the live site within a minute.

### Rendering exercises to PDF instead of HTML

Each exercise `.Rmd` has a YAML header like:

```yaml
output:
  html_document:
    toc: true
```

Swap to PDF by changing it to:

```yaml
output:
  pdf_document:
    toc: true
    toc_depth: 2
    number_sections: true
```

This requires a LaTeX install — easiest is `quarto install tinytex` (or `tinytex::install_tinytex()` in R).

You can also keep both formats by listing them:

```yaml
output:
  html_document:
    toc: true
  pdf_document:
    toc: true
```

Then **Knit** offers both options.

### Adapting for your own course

Common starting points:

- Change `_quarto.yml` `website.title` and the navbar entries.
- Replace `lectures/burn_slides.css` (or theme via `theme:` in each lecture's YAML) for different visual styling.
- Drop or add lectures by editing `lectures/`, the navbar in `_quarto.yml`, and the table in `index.qmd`.
- Swap data sources in the exercises — most use NHANES (via the `NHANES` R package) or IPUMS NHIS extracts. The IPUMS workflow is documented in `tutorials/02_eda_ipums/ipums_howto.pdf`.

If you publish your adaptation, please attribute back to this repo!

---

## Acknowledgements

Many thanks to the following people for sharing materials: Sam Asher, Scott Cunningham, Alex Hoagland, Nick Huntington-Klein, Laura Lufray, Fintan Nagle, Simon Quinn, Nicola Rennie, and Shuang Zhang.

## License

See [LICENSE](LICENSE) for terms.

## Issues and contributions

Suggestions, corrections, and pull requests welcome. Open an issue on the [GitHub repo](https://github.com/SamanthaBurn/HealthAnalytics/issues).

---

*Built with R, RStudio, and Quarto.*
