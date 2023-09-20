---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS (experimental)
css: unocss
---

# How Markdown Can Stop Hurricanes

Ben Holmes _@bholmesdev_

---

## What we're talking about

<TOC />

---
layout: intro
---

## Avoid greenwashing

> misleading or deceptive publicity disseminated by an organization so as to present an environmentally responsible public image.

---

## Avoid greenwashing

- Don't pretend scale of environmental impact
- Don't assume all efforts are on the consumer

---

## Sources of carbon emissions (VERY non exhaustive)

- Development cycle: CI/CD automation
- Database and asset storage
- Compute time per request
- Sending resources over-the-wire
- Client-side compute


- How we build our websites
- How we deploy our websites


---

## Debugging

As JS gets better, testing gets... <v-click class=""> worse? 😅 </v-click>

- Tight coupling = more to simulate

---

## Green hosting

- Not all compute hours are created equal
  - Emissions are often an industry problem far more than an individual problem
  - If you work countless hours to push compute times to zero, it's all pointless if the host is burning coal on each request

- [Cloudflare worker cron jobs can be switched to sustainable hosts](https://blog.cloudflare.com/announcing-green-compute/)
- [Cloudflare pages certified to run 100% renewable energy as Green Web Foundation partner](https://blog.cloudflare.com/green-hosting-with-cloudflare-pages/)
- [Green Web Foundation directory of hosts](https://www.thegreenwebfoundation.org/tools/directory/)