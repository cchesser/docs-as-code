---
title: "Theme"
weight: 10
description: Example of using both Docsy + reveal-hugo themes for technical documentation and slides.
---

This site also generates [presentation slides]({{< ref "/slides" >}}) that are managed through Markdown and HTML using [reveal.js](https://revealjs.com/). This is powered through the use of the [reveal-hugo theme](https://github.com/dzello/reveal-hugo), that is used in combination with the [Docsy theme](https://www.docsy.dev/).

## Configuration

The following is supplied in the `config.toml`:

```toml
theme = ["reveal-hugo", "docsy"]
```

The site is configured with the following configuration in the front-matter for the root `_index.md` file:

```yaml
cascade:
- type: "reveal"
  _target:
    path: "/slides/**"
- type: "docs"
  _target:
    path: "/**"
---
```

This results in a site that is modeled like the [mostlydocs site example](https://github.com/gwatts/mostlydocs) (which is template that you can use), to build a site that starts with a primary docs site. This excludes the more elaborate root landing page that you can format differently, if you are just really wanting to host structured documentation.