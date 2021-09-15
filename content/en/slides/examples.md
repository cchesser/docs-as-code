---
title: "Docs as Code: Examples"
weight: 20
toc_hide: true
outputs:
- Reveal
---

{{< slide id="examples" >}}

## 🚀
## Examples

<p class="fragment fade-up"><strong>🔤 Markdown</strong>: Authoring</p>
<p class="fragment fade-up"><strong>⚙️ Hugo</strong>: Generating</p>
<p class="fragment fade-up"><strong>👔 Docsy</strong>: Theming</p>
<p class="fragment fade-up"><strong>⚡️ GitHub Actions</strong>: Building</p>
<p class="fragment fade-up"><strong>📑 GitHub Pages</strong>: Serving</p>

---

## 🔤
## Markdown

Markdown is a lightweight markup language that you can use to add formatting elements to plaintext text documents. Created by John Gruber in 2004, Markdown is now one of the world’s most popular markup languages.

<small>Source: [The Markdown Guide](https://www.markdownguide.org/)</small>

---

## Editing

![](img/markdown-preview.png)

---

Great resource 👇

<a href="https://www.markdownguide.org/"><img src="img/markdown-guide.png"></a>

---

![](img/hugo-logo.png)

The world’s fastest framework for building websites

https://gohugo.io/

---

<h2>Hugo Features</h2>
<p class="fragment fade-up">🦄 Shortcodes <br />
  <small>Powerful way to extend beyond Markdown with reusable code blocks</small>
</p>
<p class="fragment fade-up">🪴 Multiple Formats <br />
  <small>Hugo allows you to output your content in multiple formats...like this presentation</small>
</p>
<p class="fragment fade-up">🦥 Flexible <br />
  <small>Build different types of content (menus, diagrams) to make a rich website out of Markdown</small>
</p>
<p class="fragment fade-up">⚡️ Speed <br />
  <small>At < 1 ms per page, the average site builds in less than a second</small>
</p>

---

{{< slide id="docsy-announced" background-image="img/docsy-announced.png" background-opacity="0.8" transition-speed="fast" >}}

<div class="fragment fade-in-then-out" style="background: rgb(0, 0, 0); background: rgba(0, 0, 0, 0.8);">
<a href="https://opensource.googleblog.com/2019/07/announcing-docsy-website-theme-for.html" target="_blank"><h3>Open-sourced July 2019!</h3></a>
</div>

---

{{< slide id="docsy-example" background-image="img/docsy-example.png" background-opacity="0.8" transition-speed="fast" >}}

<div style="background: rgb(0, 0, 0); background: rgba(0, 0, 0, 0.8);">
A <a href="https://opensource.googleblog.com/2019/07/announcing-docsy-website-theme-for.html" target="_blank">Hugo theme</a> for creating great technical documentation sites
</div>

---

## 👔
## Docsy Examples

<div class="r-stack">
  <img class="fragment fade-up" src="img/docsy-grpc.png" />
  <img class="fragment fade-up" src="img/docsy-spinnaker.png" />
  <img class="fragment fade-up" src="img/docsy-kubernetes.png" />
</div>

---

## 🦄
## Shortcodes

Generate API documentation from your OpenAPI (Swagger) specifications.

<pre><code style="text-align: center">{{</* swaggerui src="/openapi/petstore.yaml" */>}}
</code></pre>

---

## 🧜‍♀️ 
## Diagrams: Mermaid

<pre><code data-line-numbers="2|3|4-6">
```mermaid
graph LR
  Start --> Need{"Do I need diagrams"}
  Need -- No --> Off["Set params.mermaid.enable = false"]
  Need -- Yes --> HaveFun["Great!  Enjoy!"]
```
</code></pre>

<img style="background-color: white" src="img/mermaid-example.svg" />

---

## GitHub Actions

Build your docs! 

<small>Include in `.github/workflows/gh-pages.yaml` file.</small>

<pre><code data-line-numbers="3-7|46-51">name: github pages

on:
  push:
    branches:
      - main
  pull_request:

jobs:
  deploy:
    runs-on: ubuntu-20.04
    concurrency:
      group: ${{ github.workflow }}-${{ github.ref }}
    steps:
      - uses: actions/checkout@v2
        with:
          submodules: recursive  # Fetch the Docsy theme
          fetch-depth: 0         # Fetch all history for .GitInfo and .Lastmod

      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          # Can pin to a specific version if needed, ex:
          # hugo-version: '0.79.1'
          hugo-version: 'latest'
          extended: true

      - name: Setup Node
        uses: actions/setup-node@v2
        with:
          node-version: '14'

      - name: Cache dependencies
        uses: actions/cache@v1
        with:
          path: ~/.npm
          key: ${{ runner.os }}-node-${{ hashFiles('**/package-lock.json') }}
          restore-keys: |
            ${{ runner.os }}-node-

      - run: npm ci
      - run: hugo
        env:
          HUGO_ENV: production

      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        if: ${{ github.ref == 'refs/heads/main' }}
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_branch: gh-pages</code></pre>


---

## 📑
## GitHub Pages

<p class="fragment fade-up">⚒️ Build and test your docs on pull requests</p>
<p class="fragment fade-up">🧆 Generate and store static content for serving</p>

---

## 🧪
## Try it out!

Try out <a href="/docs-as-code" target="_self" >the example site</a> by:

<p class="fragment fade-up">✍️ Use <em>Edit this Page</em> to make a change via a PR</p>
<p class="fragment fade-up">⚙️ See build process on pull request and preview</p>
