---
title: "Docs as Code: History"
weight: 10
toc_hide: true
outputs:
- Reveal
---

{{< slide id="intro" >}}

Fantastic resource 👇

<a href="https://www.writethedocs.org/guide/docs-as-code/"><img src="img/write-the-docs.png" width="400"></a>

---

## Docs as Code?

Documentation as Code (Docs as Code) refers to a philosophy that you should be writing documentation with the _same tools as code_.

<small><em>Source: <a href="https://www.writethedocs.org/guide/docs-as-code/">Write the Docs</a></em></small>

---

<h2>Docs as Code uses...</h2>
<small><em>Source: <a href="https://www.writethedocs.org/guide/docs-as-code/">Write the Docs</a></em></small>
<p class="fragment fade-up">🐞 Issue Trackers</p>
<p class="fragment fade-up">🌳 Version Control (git)</p>
<p class="fragment fade-up">🔤 Plain Text Markup<br /><small>(Markdown, reStructuredText, Asciidoc)</small></p>
<p class="fragment fade-up">💬 Code Reviews</p>
<p class="fragment fade-up">✅ Automated Tests</p>

---

## 🐞 Issue Trackers

Align tracking the work of documentation with code. 
<small>(have it live in the same queue)</small>

---

<h2>🌳 Version Control (git)</h2>
<p class="fragment fade-up">Enable docs and code to live in same changeset<br /><small>(like your tests)</small></p>
<p class="fragment fade-up">Enable concurrent development branches</p>
<p class="fragment fade-up"><small>🌈 Enable all the features of version control for your documentation!</small></p>

---

## 🔤 Plain Text Markup

Enable all the features of your code editors in documentation<br />
<small>
(compare, find/replace, track in version control)
<p class="fragment fade-up">🌈 Many editors with preview mode for Markdown as you edit!</p>
</small>

---

## 💬 Code Reviews

Enable discussions with code using the same toolchain 
<small>(line-by-line comments, suggestions they can apply, CODEOWNERS)</small>

---

## ✅ Automated Tests

Enable static analysis tests on documentation
<small>(status checks on pull requests)</small>

---

{{< slide id="background" background-image="img/twitter-docs.png" background-opacity="0.8" transition-speed="fast" >}}

<div class="fragment fade-out" style="background: rgb(0, 0, 0); background: rgba(0, 0, 0, 0.8); padding: 10px;">
<h2>Creating the Culture of Documentation</h2><br /></a>
<a href="https://youtu.be/6y4eQ6gYwdU" target="_blank"><small>Write the Docs (Twitter, 2014)</small></a>
</div>

---

{{< slide id="google" background-image="img/google-docs-1.png" background-opacity="0.8" transition-speed="fast" >}}

<div class="fragment fade-out" style="background: rgb(0, 0, 0); background: rgba(0, 0, 0, 0.8); padding: 10px; position: absolute; bottom: 0">
  <h3>Documentation, Disrupted</h3>
  <h4>How Two Technical Writers Changed Google Engineering Culture</h4>
<a href="https://youtu.be/EnB8GtPuauw" target="_blank"><small>Write the Docs (Google, 2015)</small></a>
</div>

---

{{< slide id="spotify" background-image="img/spotify-docs-2.png" background-opacity="0.8" transition-speed="fast" >}}

<div class="fragment fade-out" style="background: rgb(0, 0, 0); background: rgba(0, 0, 0, 0.8); padding: 10px; position: absolute; bottom: 0">
  <h3>How we are solving internal technical documentation at Spotify</h3>
<a href="https://youtu.be/uFGCaZmA6d4" target="_blank"><small>Write the Docs (Spotify, 2019)</small></a>
</div>

---

{{< slide id="spotify-techdocs" background-image="img/spotify-techdocs.png" background-opacity="0.8" transition-speed="fast" >}}

<div class="fragment fade-in-then-out" style="background: rgb(0, 0, 0); background: rgba(0, 0, 0, 0.8); padding: 10px; position: absolute; bottom: 0">
<a href="https://backstage.io/blog/2020/09/08/announcing-tech-docs" target="_blank"><h3>Open-sourced September 2020!</h3></a>
</div>

---

<h2>Problematic Signals</h2>
<p class="fragment fade-up">🏝 Islands of documentation<br /><small>(MediaWiki, Confluence, Office 365, READMEs, GitHub Pages)</small></p>
<p class="fragment fade-up">📜 Excessive documentation decay <br /><small>(possibly caused by  islands)</small></p>
<p class="fragment fade-up">🔍 Searchability challenges</p>
<p class="fragment fade-up">🤷‍♂️ Different process for maintaining (vs. with code)</p>
<p class="fragment fade-up">😐 Lack of trust on the content</p>

---

<section data-auto-animate>
  <p id="prob">🏝 Islands of documentation<br /><small>(MediaWiki, Confluence, Office 365, READMEs, GitHub Pages)</small><br />
  📜 Documentation decay due to islands<br />
  🔍 Searchability challenges<br />
  </p>
</section>
<section data-auto-animate>
  <p id="prob" style="font-size: smaller; opacity: 0.2;">🏝 Islands of documentation<br /><small>(MediaWiki, Confluence, Office 365, READMEs, GitHub Pages)</small><br />
  📜 Documentation decay due to islands<br />
  🔍 Searchability challenges<br />
  </p>
  <p>🌎 A centralized build system for documentation that can enable content through a common convention</p>
</section>

---

<section data-auto-animate>
  <p id="prob">🤷‍♂️ Different process for maintaining (vs. with code)</p>
</section>
<section data-auto-animate>
  <p id="prob" style="font-size: smaller; opacity: 0.2;">🤷‍♂️ Different process for maintaining (vs. with code)</p>
  <p>🧰 Enable documentation to exist closer to the code and toolchain</p>
</section>

---

<section data-noprocess>
  <section data-auto-animate>
    <p id="prob">😐 Lack of trust on the content</p>
  </section>
  <section data-auto-animate>
    <p id="prob" style="font-size: smaller; opacity: 0.2;">😐 Lack of trust on the content</p>
    <p>🪄 Make it easy for anyone to contribute<br />
    <small>help them along the way, like DocDays!</small></p>
  </section>
</section>

---

But, not everyone has GitHub access...
<p class="fragment fade-up">or knows Markdown.<br />
🤷‍♂️
</p>

---

## 🧩 

Ensure approach aligns with strategy for expected toolchain access<br />
<small>(GitHub Enterprise)</small>

---

## 🔤

Illustrate through examples that if <u>you know text</u>, <br />you <u>can write Markdown</u><br />
<small>Majority of contributions = textual content, ≠ formatting</small>
