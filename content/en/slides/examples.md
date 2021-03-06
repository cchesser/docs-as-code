---
title: "Docs as Code: Examples"
weight: 20
toc_hide: true
outputs:
- Reveal
---

{{< slide id="examples" >}}

## ð
## Examples

<p class="fragment fade-up"><strong>ð¤ Markdown</strong>: Authoring</p>
<p class="fragment fade-up"><strong>âï¸ Hugo</strong>: Generating</p>
<p class="fragment fade-up"><strong>ð Docsy</strong>: Theming</p>
<p class="fragment fade-up"><strong>â¡ï¸ GitHub Actions</strong>: Building</p>
<p class="fragment fade-up"><strong>ð GitHub Pages</strong>: Serving</p>

---

## ð¤
## Markdown

Markdown is a lightweight markup language that you can use to add formatting elements to plaintext text documents. Created by John Gruber in 2004, Markdown is now one of the worldâs most popular markup languages.

<small>Source: [The Markdown Guide](https://www.markdownguide.org/)</small>

---

## Editing

![](img/markdown-preview.png)

---

Great resource ð

<a href="https://www.markdownguide.org/"><img src="img/markdown-guide.png"></a>

---

![](img/hugo-logo.png)

The worldâs fastest framework for building websites

https://gohugo.io/

---

<h2>Hugo Features</h2>
<p class="fragment fade-up">ð¦ Shortcodes <br />
  <small>Powerful way to extend beyond Markdown with reusable code blocks</small>
</p>
<p class="fragment fade-up">ðª´ Multiple Formats <br />
  <small>Hugo allows you to output your content in multiple formats...like this presentation</small>
</p>
<p class="fragment fade-up">ð¦¥ Flexible <br />
  <small>Build different types of content (menus, diagrams) to make a rich website out of Markdown</small>
</p>
<p class="fragment fade-up">â¡ï¸ Speed <br />
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

## ð
## Docsy Examples

<div class="r-stack">
  <img class="fragment fade-up" src="img/docsy-grpc.png" />
  <img class="fragment fade-up" src="img/docsy-spinnaker.png" />
  <img class="fragment fade-up" src="img/docsy-kubernetes.png" />
</div>

---

## ð¦
## Shortcodes

Generate API documentation from your OpenAPI (Swagger) specifications.

<pre><code style="text-align: center">{{</* swaggerui src="/openapi/petstore.yaml" */>}}
</code></pre>

---

## ð§ââï¸ 
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

## GitHub Actions

Test your docs (spellcheck)!

<small>Include in `.github/workflows/validation.yaml` file.</small>

<pre><code data-line-numbers="3-7|20">name: validation

on:
  push:
    branches:
      - main
  pull_request:

jobs:
  spell-check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
        name: Check out the code
      - uses: actions/setup-node@v1
        name: Run spell check
        with:
          node-version: "12"
      - run: npm install -g cspell
      - run: cspell lint --config .github/cspell.json "content/**/*.md"</code></pre>

---

## GitHub Actions

â Enforce your tests in pull requests

<div class="r-stack">
<img class="fragment" src="img/pr-fail-1.png" />
<img class="fragment" src="img/pr-fail-2.png" />
</div>

---

## ð
## GitHub Pages

<p class="fragment fade-up">âï¸ GitHub Actions build content on PRs and main</p>
<p class="fragment fade-up">ð§ Generate and store static content for serving</p>

---

## ð§ª
## Try it out!

<a href="/docs-as-code" target="_self" >https://cchesser.github.io/docs-as-code/</a>

<p class="fragment fade-up">âï¸ Try the <em>Edit this Page</em> link to make a change via a PR</p>
<p class="fragment fade-up">âï¸ See build process on pull request and preview</p>
