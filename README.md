# Repository Setup

## Site Content Workflow (Quarto)

This site is built using [Quarto](https://quarto.org/) and utilizes a "render to root" workflow for GitHub Pages hosted on the `main` branch. The workflow involves rendering content locally and then pushing the generated static files to GitHub Pages.

1.  **Edit Source Files:** Make changes to the `.qmd` (Quarto Markdown) source files (e.g., `index.qmd`, `projects.qmd`).
2.  **Render Site Locally:** After making changes, generate the static HTML files by running Quarto's render command in your terminal from the root of the repository:
    ```bash
    quarto render
    ```
    This command will convert your `.qmd` files into corresponding `.html` files (e.g., `index.qmd` -> `index.html`).
3.  **Commit and Push:** Stage both your modified `.qmd` source files and the newly generated or updated `.html` output files, then commit and push them to the `main` branch:
    ```bash
    git add .
    git commit -m "feat: updated site content"
    git push origin main
    ```
    GitHub Pages will then automatically serve the updated HTML files.

**Important:** It is crucial to run `quarto render` and commit the generated `.html` files whenever you update your `.qmd` source files. If you only push the `.qmd` files, the live website will not reflect your changes.