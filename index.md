---
layout: default
---

<div id="intro">
  <h1>State of Palestine</h1>
  <p>{{ site.description }}</p>
  <div id="cta">
    <a href="{{ site.data.cta.link }}">
      {{ site.data.cta.text }}
    </a>
  </div>
</div>

<div id="images">
  {% for image in site.data.images %}
    <figure>
      <img src="/{{ site.baseurl }}{{ site.data.assets.path }}{{ image.name }}" loading="lazy" width="500" height="500" />
      <figcaption>
        {{ image.name }}
      </figcaption>
    </figure>
  {% endfor %}
</div>

<style>
  html,
  body {
    position: relative;
    top: 0;
    left: 0;
    width: 100%;
    min-height: 100%;
    font-size: 13px;
    font-family: monospace;
    font-weight: 400;
    font-style: normal;
    line-height: 1.3;
    color: #000;
    scroll-behavior: smooth;
    background: #f8f8f8;
  }
  *,
  *::before,
  *::after {
    margin: 0;
    padding: 0;
    font-size: inherit;
    font-family: inherit;
    font-weight: inherit;
    font-style: inherit;
    line-height: inherit;
    color: inherit;
    font-synthesis: none;
    text-align: inherit;
    text-decoration: inherit;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    text-rendering: optimizeLegibility;
    -webkit-text-size-adjust: 100%;
    -moz-text-size-adjust: 100%;
    -ms-text-size-adjust: 100%;
    text-size-adjust: 100%;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    word-wrap: break-word;
    overflow-wrap: break-word;
    touch-action: manipulation;
  }
  :root {
    --gap: 2rem;
  }
  body {
    display: flex;
    flex-direction: column;
    padding-inline: calc(var(--gap) + env(safe-area-inset-left, 0px));
  }
  body > * {
    padding-block: var(--gap);
  }
  #intro {
    position: sticky;
    top: 0;
    display: flex;
    flex-direction: column;
    gap: calc(var(--gap) / 2);
    padding-block: var(--gap);
    border-block-end: 1px solid #ddd;
    background: #f8f8f8;
  }
  #intro > h1 {
    font-size: 2rem;
    font-weight: bold;
    line-height: 1.0;
  }
  #cta > a {
    display: block;
    width: fit-content;
    padding: calc(var(--gap) / 3);
    border-radius: 5px;
    background: #f8f8f8;
    color: #000;
    border: 1px solid #000;
  }
  @media (any-hover: hover) {
    #cta > a:hover {
      background: #000;
      color: #f8f8f8;
    }
  }
  #images {
    display: flex;
    flex-wrap: wrap;
    gap: var(--gap);
    --columns: 3;
  }
  @media (max-width: 1024px) {
    #images {
      --columns: 2;
    }
  }
  @media (max-width: 640px) {
    #images {
      --columns: 1;
    }
  }
  #images > figure {
    flex-basis: calc((100% - ((var(--columns) - 1) * var(--gap))) / var(--columns));
  }
  #images > figure > img {
    aspect-ratio: 1/1;
    display: block;
    width: 100%;
    height: auto;
    object-fit: contain;
  }
  #images > figure > figcaption {
    margin-block-start: calc(var(--gap) / 3);
  }
</style>
