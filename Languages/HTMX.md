# htmx.org.home
## introduction

htmx gives you access to [AJAX](https://htmx.org/docs/#ajax), [CSS Transitions](https://htmx.org/docs/#css_transitions), [WebSockets](https://htmx.org/docs/#websockets) and [Server Sent Events](https://htmx.org/docs/#sse) directly in HTML, using [attributes](https://htmx.org/reference/#attributes), so you can build [modern user interfaces](https://htmx.org/examples/) with the [simplicity](https://en.wikipedia.org/wiki/HATEOAS) and [power](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm) of hypertext

htmx is small ([~14k min.gz’d](https://unpkg.com/htmx.org/dist/)), [dependency-free](https://github.com/bigskysoftware/htmx/blob/master/package.json), [extendable](https://htmx.org/extensions/), IE11 compatible & has **reduced** code base sizes by [67% when compared with react](https://htmx.org/essays/a-real-world-react-to-htmx-port/)

## motivation

- Why should only [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) and [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) be able to make HTTP requests?
- Why should only [`click`](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event) & [`submit`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit_event) events trigger them?
- Why should only [`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) & [`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) methods be [available](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)?
- Why should you only be able to replace the **entire** screen?

By removing these arbitrary constraints, htmx completes HTML as a [hypertext](https://en.wikipedia.org/wiki/Hypertext)

## quick start

```html
  <script src="https://unpkg.com/htmx.org@1.9.10"></script>
  <!-- have a button POST a click via AJAX -->
  <button hx-post="/clicked" hx-swap="outerHTML">
    Click Me
  </button>
```

The [`hx-post`](https://htmx.org/attributes/hx-post/) and [`hx-swap`](https://htmx.org/attributes/hx-swap/) attributes on this button tell htmx:

> “When a user clicks on this button, issue an AJAX request to /clicked, and replace the entire button with the HTML response”

htmx is the successor to [intercooler.js](http://intercoolerjs.org/)

Read the [docs introduction](https://htmx.org/docs/#introduction) for a more in-depth… introduction.

## book

We are happy to announce the release of [Hypermedia Systems](https://hypermedia.systems/), a book on how to build [Hypermedia-Driven Applications](https://htmx.org/essays/hypermedia-driven-applications/) using htmx & more:

[![hypermedia systems](https://htmx.org/img/hypermedia-systems.png)](https://www.amazon.com/dp/B0C9S88QV6/ref=sr_1_1?crid=1P0I3GXQK32TN)



# docs
[</> htmx ~ Documentation](https://htmx.org/docs/#ajax)

# examples
[</> htmx ~ Examples](https://htmx.org/examples/)
[</> htmx ~ A Real World React -> htmx Port](https://htmx.org/essays/a-real-world-react-to-htmx-port/)
# playgrounds
[HTML Online Viewer](https://html.onlineviewer.net/)
[HTMX Playground (playcode.io)](https://playcode.io/1716471)
[HTMX Playground (htmx-playground.vercel.app)](https://htmx-playground.vercel.app/)

# comparisons
down:: [[HTMXvsReact]]

# combos
down:: [[HTMX-hyperscript]]
down:: [[HTMX-React]]

# other
podcast - [HTMX, Hyperscript, and More! | HTML All The Things](https://www.htmlallthethings.com/blog-posts/htmx-hyperscript-and-more)
