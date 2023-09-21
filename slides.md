---
theme: seriph 
layout: cover
transition: slide-fade
background: /nasa-hurricane.avif
defaults:
  transition: fade
  layout: center
class: 'text-center'
highlighter: shiki
css: unocss
fonts:
  sans: "Atkinson Hyperlegible"
  weights: "400,700"
---

# How Markdown Can Stop Hurricanes

Ben Holmes _@bholmesdev_

---
layout: cover
background: /kristaps-ungurs--lNJUtc6CPw-unsplash.jpg
---

## **Problem:** the earth's getting toasty 😓

<p class="text-2xl" v-click>

And the web contributes <span class="font-bold text-orange-500">~2%</span> of emissions

</p>

<Footnote>

BBC science focus: https://www.sciencefocus.com/science/what-is-the-carbon-footprint-of-the-internet

</Footnote>

---
layout: cover
background: /kristaps-ungurs--lNJUtc6CPw-unsplash.jpg
---

## We're all content authors here!

<v-click>

What do we contribute, and how can we improve?

</v-click>

---
layout: cover
background: /kristaps-ungurs--lNJUtc6CPw-unsplash.jpg
---

## Goals

<v-clicks>

✅ explore energy-efficient **hosting, developing, and debugging**

✅ find wins that won't sacrifice usability or developer experience

</v-clicks>

---

<div class="max-w-prose m-auto">

## Let's not pretend it's _our_ problem

> **Greenwashing:** misleading or deceptive publicity disseminated by an organization so as to present an environmentally responsible public image.

<v-click>

**Companies** have a larger impact than the **consumer.**

</v-click>

</div>

---
layout: image-right
image: /cloud-hosts.png
---

## Hosting


Most energy spent **computing and sending.**

<v-clicks>

- How are the host's servers powered? 
- What's the distance content ➡️ user?
- Static? Cached? On-demand?

</v-clicks>


---
layout: image-right
image: /cloud-hosts.png
---

## Hosting


Most energy spent **computing and sending.**

- How are the host's servers powered? <span class="text-blue-400 font-bold">them</span> 
- What's the distance content ➡️ user? <span class="text-yellow-400 font-bold">us</span>
- Static? Cached? On-demand? <span class="text-green-400 font-bold">us _and_ them</span>

---

## **Them:** Know what servers they use

<v-clicks>

Visit the <span class="text-green-400 font-bold">Green Web Foundation directory</span>

Case: **Cloudflare** 🌥️

- Worker cron jobs can be switched to sustainable hosts
- Pages certified 100% renewable energy

</v-clicks>

<Footnote>

Green Web Foundation directory https://www.thegreenwebfoundation.org/tools/directory/

Cloudflare green compute https://blog.cloudflare.com/announcing-green-compute/

Cloudflare pages https://blog.cloudflare.com/green-hosting-with-cloudflare-pages/

</Footnote>

---

## **Us:** Know where content comes from

---


<FlipOnClick>

![](/lifecycle-hype.png)

</FlipOnClick>

---

![](/lifecycle-ideal.png)

---

## Make development <span class="font-bold text-green-400">us _and_ them</span>

<v-clicks>

- <span class="font-bold text-yellow-400">Us:</span> Our product
- <span class="font-bold text-blue-400">Them:</span> The framework

</v-clicks>

---

## Next and SvelteKit runtimes


<div grid="~ cols-2 gap-4">
<div>

- **✨ Magic:** Default to static, dynamic when you use `cookies`, `Response`, or query params
- **🔨 Manual:** Per-route runtime options

</div>
<div>

```ts
// cached, with revalidation options
fetch('https://...', { next: { revalidate: 3600 } });

export const runtime = 'edge' // 'nodejs' (default) | 'edge'
```

</div>
</div>

---

## For server / client: let's talk **opt-in**

---
src: ./chapters/complexity-line.md
---

---

## Opt-in to compute 💚

<v-clicks>

- Server, then client
- Prerendered, then on-demand (remember **Jamstack?**)
- Static, then server(less)(edge)

</v-clicks>

---
layout: iframe-right
url: https://starlight.astro.build/environmental-impact/#comparisons
---

## Where Markdown stops hurricanes

_Enter VC funding mode_ 😉

If we pulled our <span class="text-orange-400 font-bold">1.17g</span> page-view emissions down to the cost of HTML **(< 0.01g)**, we could make a <span class="text-green-400 font-bold">1.98%</span> dent

<Footnote>

Website carbon calculator https://www.websitecarbon.com/

</Footnote>

---

## We've deployed... now we maintain

**Debugging:** What do you have to **mock, compile, and run-rerun-rerun** to find the problem?

---
layout: image-right
image: /coupling-the-good.png
---

## Debugging

<span class="text-green-600">The good:</span> Web dev is spoiled by instant feedback loops

<v-clicks>

- **Counting milliseconds** per dev server update
- **Hot module reloading** to preserve client state
- **JS across the stack:** one language, fewer probs

</v-clicks>

---
layout: image-right
image: /trello-clone-meme.png
---

## Debugging

<span class="text-red-600">The bad:</span> More tooling = more points of failure

<v-clicks>

- Blurred server / client boundaries = wacky bundling
- Endpoints are tightly coupled with RPC
- TypeScript requires a build step (sorry mocha and chai)
- **Left to console logs** most of the time

</v-clicks>

---
layout: image
image: /fix-lint.png
---

<Popover>

**CI and prod-only** bugs are still too common 😓

- Fast dev servers like Vite = _not_ prod builds
- Edge runtimes = special _ahem_ edge cases

</Popover>

---
layout: image-right
image: /kristaps-ungurs--lNJUtc6CPw-unsplash.jpg
---

## Debugging and CI/CD

Every CI/CD trigger costs compute.

<v-clicks>

- ⬆️ with environments (Linux, Mac, Windows)
- ⬆️ with build processes (TypeScript, Webpack, Vite)
- ⬆️ with reruns to `console.log` in prod

</v-clicks>

---

## New debuggers?

<Gif src="/replayio.mp4" controls class="h-128" />

<Popover>

## Replay.io 

Small storage, zero rebuilds, only load replay on-demand

</Popover>

---
layout: image-right
image: /svelte-jsdoc.png
---

## Less bundling?

Case: Svelte ditched `.ts` for core packages

<v-clicks>

- 🧘‍♂️ Kept type-safety with JSDoc and user-facing `.d.ts`
- 🔪 Cut **release and CI build costs** to basically zero
- TypeScript's `tsc` step = up to 4x higher energy cost

</v-clicks>

<Footnote class="max-w-[50vw]">

Energy efficiency across programming languages https://greenlab.di.uminho.pt/wp-content/uploads/2017/09/paperSLE.pdf

</Footnote>

---

## Better dev /prod alignment?

<v-clicks>

- **Turbopack** wants prod builds in dev without the wait
- **Cloudflare's wrangler** replicates worker environments locally
- **AWS Cloud9** puts the editor where code is running

</v-clicks>

---
layout: cover
background: /nasa-hurricane.avif
---

## So... can Markdown stop hurricanes?

<v-click>

If we compute less, opt-in more, and debug beyond the `console.log`... I think it can 🙃

</v-click>

---

## Thank you!

- 🚀 **Astro discord** - [astro.build/chat](https://astro.build/chat)
- 🔎 **@bholmesdev** everywhere - [wtw.dev](https://wtw.dev)
- 🍔 **Slides** - [**github.com/bholmesdev**/how-markdown-can-stop-hurricanes](https://github.com/bholmesdev/how-markdown-can-stop-hurricanes)
