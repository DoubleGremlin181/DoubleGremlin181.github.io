# ReIndigo

A minimalist Jekyll template for personal websites and blogs.

<p align="center">
    <img src="https://raw.githubusercontent.com/DoubleGremlin181/ReIndigo/gh-pages/assets/screen-shot.png" />
</p>

<p align="center">
    <a href="https://reindigo.kavi.sh/">Demo</a>
</p>

## About

ReIndigo is a fork of [Indigo](https://github.com/sergiokopplin/indigo) by [Sérgio Kopplin](https://github.com/sergiokopplin), with additional features and enhancements.

## Enhancements over Indigo

- **Interactive plots** — Embed [Bokeh](https://bokeh.org/) visualizations in posts
- **LaTeX support** — Render math equations with [MathJax](https://www.mathjax.org/)
- **Enhanced tags page** — Tags counted and sorted by frequency
- **`/resume` vanity URL** — Clean redirect with Google Analytics tracking
- **Auto dark mode** — Follows system preference with `dark-theme: auto`
- **Automatic sitemap** — Generated via `jekyll-sitemap` for SEO

## Setup

1. Fork the project [ReIndigo](https://github.com/DoubleGremlin181/ReIndigo/fork)
2. Edit `_config.yml` with your data
3. Write some posts

### Running locally

```sh
docker compose up
```

Then open [http://localhost:4000](http://localhost:4000)

<details>
<summary>Without Docker</summary>

```sh
bundle install
bundle exec jekyll serve
```
</details>

## Settings

Customize your site in `_config.yml`. See the [FAQ](./FAQ.md) for detailed configuration options.

## License

[MIT](https://opensource.org/licenses/MIT) License

Original [Indigo](https://github.com/sergiokopplin/indigo) theme © Sérgio Kopplin
