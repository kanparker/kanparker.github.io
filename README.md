# Repository Setup

This repository uses [Git Large File Storage (LFS)](https://git-lfs.com/) to manage large binary files such as images and PDFs. This is important for keeping the repository size manageable.

## Git LFS Setup Instructions

If you are cloning this repository for the first time or encountering issues with binary files (e.g., they appear as small text pointers), you need to ensure Git LFS is properly set up on your machine.

1.  **Install Git LFS:**
    First, install Git LFS. The installation method varies by operating system:

    *   **macOS (using Homebrew):**
        ```bash
        brew install git-lfs
        ```
    *   **Ubuntu/Debian:**
        ```bash
        sudo apt-get install git-lfs
        ```
    *   **Windows:**
        Download and run the installer from the [Git LFS website](https://git-lfs.com/).

2.  **Initialize Git LFS for your system:**
    After installation, run this command once to set up Git LFS for your user account:
    ```bash
    git lfs install
    ```

3.  **Clone the repository (or pull existing files):**
    If you're cloning the repository for the first time, Git LFS will automatically download the large files after the clone:
    ```bash
    git clone [repository-url]
    ```
    If you have already cloned the repository and then installed Git LFS, or if some large files appear as pointers, you can fetch the actual content by running:
    ```bash
    git lfs pull
    ```

Following these steps will ensure that all large files are correctly handled when you clone or work with this repository.

## Site Content Workflow (Quarto)

This site is built using [Quarto](https://quarto.org/). The workflow involves rendering content locally and then pushing the generated static files to GitHub Pages.

1.  **Edit Source Files:** Make changes to the `.qmd` (Quarto Markdown) source files (e.g., `index.qmd`, `projects.qmd`).
2.  **Render Site Locally:** After making changes, generate the static HTML files by running Quarto's render command in your terminal from the root of the repository:
    ```bash
    quarto render
    ```
    This command will convert your `.qmd` files into corresponding `.html` files (e.g., `index.qmd` -> `index.html`).
3.  **Commit and Push:** Stage both your modified `.qmd` source files and the newly generated or updated `.html` output files, then commit and push them to the `gh-pages` branch:
    ```bash
    git add .
    git commit -m "feat: updated site content"
    git push origin gh-pages
    ```
    GitHub Pages will then automatically serve the updated HTML files.

**Important:** It is crucial to run `quarto render` and commit the generated `.html` files whenever you update your `.qmd` source files. If you only push the `.qmd` files, the live website will not reflect your changes.