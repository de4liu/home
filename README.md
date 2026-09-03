# Dr. De Liu — academic site

Live: [https://de4liu.github.io/home/](https://de4liu.github.io/home/)

Jekyll site based on [academicpages](https://academicpages.github.io/) (Minimal Mistakes lineage). **Agent / maintainer guide:** [`AGENTS.md`](AGENTS.md).

## Local preview

```bash
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
# http://127.0.0.1:4000/home/
```

If `bundle install` fails on Linux because of Windows platform gems in `Gemfile.lock`, delete `Gemfile.lock` and install again.

## Content

Edit pages under `_pages/`. Put public PDFs in `files/`. Site config: `_config.yml`. Nav: `_data/navigation.yml`.

Pushing `master` publishes via GitHub Pages.
