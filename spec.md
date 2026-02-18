# Repository Specification: AndrewRWilliams.github.io

## Overview
This repository hosts the personal academic website for Andrew R. Williams ("FranglAI"). It is a static site built with **Jekyll** and hosted on **GitHub Pages**. using a custom **Tufte CSS** theme.

## Architecture
- **Generator**: Jekyll 3.9.x (via `github-pages` gem)
- **Theme**: Custom port of Tufte CSS (`tufte-css-jekyll`).
- **Hosting**: GitHub Pages (served from `gh-pages` branch, built by Actions).
- **CI/CD**: GitHub Actions workflow (`.github/workflows/jekyll.yml`).

## Workflow
The goal of this repository is "Maximum Simplicity".
1.  **Edit**: Create or modify Markdown files in `_posts/` or other content directories.
2.  **Push**: Commit changes and push to the `master` branch.
3.  **Deploy**: GitHub Actions automatically builds the site and deploys it. No local build required.

## Key Directories
- **`_posts/`**: Blog posts (Markdown). Format: `YYYY-MM-DD-title.md`.
- **`_plugins/`**: Custom Ruby scripts to extend Jekyll with Tufte features.
    - `sidenote.rb`, `marginnote.rb`: Add Tufte-style notes.
    - `main_column_img.rb`, `fullwidth.rb`: Image layout helpers.
    - `epigraph.rb`, `newthought.rb`: Typography helpers.
    - `mathjaxtag.rb`: LaTeX math support.
- **`assets/`**: Static assets (CSS, images, fonts).
- **`_layouts/`**: HTML templates (`default.html`, `post.html`, `page.html`).
- **`_includes/`**: Reusable HTML snippets (header, footer).

## Custom Syntax (Plugins)
The site uses custom Liquid tags to support the Tufte layout:

| Tag | Usage | Description |
| :--- | :--- | :--- |
| `{% raw %}{% sidenote id 'Note text' %}{% endraw %}` | Sidenote in the margin (numbered). |
| `{% raw %}{% marginnote id 'Note text' %}{% endraw %}` | Margin note (unnumbered). |
| `{% raw %}{% newthought 'Text' %}{% endraw %}` | Renders text in small caps. |
| `{% raw %}{% epigraph 'Quote' 'Author' %}{% endraw %}` | Blockquote with attribution. |
| `{% raw %}{% maincolumn 'img.jpg' 'Cap' %}{% endraw %}` | Image constrained to text column. |
| `{% raw %}{% fullwidth 'img.jpg' 'Cap' %}{% endraw %}` | Image spanning full page width. |

## Local Development (Optional)
Prerequisites: Ruby 3.x, Bundler.
```bash
bundle install
bundle exec jekyll serve
```
Access at `http://localhost:4000`.
