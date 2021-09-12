---
title: "Introduction"
weight: 10
description: This site is intended to host some common references and introductory content on Docs as Code.
cascade:
- type: "reveal"
  _target:
    path: "/slides/**"
- type: "docs"
  _target:
    path: "/**"
---

## What is Docs as Code?

As defined by _[Write the Docs](https://www.writethedocs.org/guide/docs-as-code/)_:

> Documentation as Code (Docs as Code) refers to a philosophy that you should be writing documentation with the same tools as code:
> 
> * Issue Trackers
> * Version Control (Git)
> * Plain Text Markup (Markdown, reStructuredText, Asciidoc)
> * Code Reviews
> * Automated Tests

## History

There are some valuable talks that cover approaches at different companies when dealing with Docs as Code. These talks helps share approaches with common motivators that support the Docs as Code approach.

### 2014: Creating the Culture of Documentation

In this talk, they shared similar struggles of documentation being in different locations, not being well-maintained, and how they focused on the problem on documentation maintainability from the engineer’s perspective. They ended up making a convention of how they treat their docs like code to improve how documentation is maintained with code changesets. This resulted in making common documentation templates (Overview, Getting Started, etc) as part of every project, and having the build system publish this in one central location. They called this build platform: Docbird. They realized they had to change the culture on documentation, but that required listening to engineers to find out how to make this valuable to them.

{{< youtube 6y4eQ6gYwdU >}}

### 2015: Documentation, Disrupted: How Two Technical Writers Changed Google Engineering Culture

The following year, Riona MacNamara from Google shared a talk at Write the Docs on how this Twitter talk influenced them in changing their culture. They found the same challenges with their documentation, where the problem wasn’t that there was enough documentation, but rather it was outdated and untrustworthy. They joked that they are the best in the world at indexing information, but that wasn’t true for their internal technical documentation. When people didn’t trust documentation, the authority was the code. This introduced productivity challenges, as different team members would have to discover more facts by going into codebases. Like code, documentation is both an asset and a liability to maintain. They then followed a similar approach to Twitter, where they had teams source their documentation in their codebase with a common convention (Markdown files in a “docs” directory). Content would get built in their central build system and it would be centrally referenced through a single portal. The name of their documentation platform was g3doc (you may see references to it when you [search their open-source projects](https://github.com/search?q=g3doc+org%3Agoogle&type=code)).

{{< youtube EnB8GtPuauw >}}

### 2019: How we are solving internal technical documentation at Spotify

Finally, this was further expanded with Spotify in 2019 that referenced what Google had applied. They called this [TechDocs](https://backstage.io/blog/2020/09/08/announcing-tech-docs), where docs are treated like code. Documentation templates and a central location that hosts this rendered content (Markdown generated into HTML) is searchable and better maintained since it lives close to the codebase and follows the same toolchain of their software development process (ex. GitHub). They have later shared this through [their open-source project call Backstage](https://backstage.io/) (a CNCF sandbox project).

{{< youtube uFGCaZmA6d4 >}}
