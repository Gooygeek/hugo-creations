# hugo-creations

A Hugo theme to showcase projects and news while linking to a separate site for selling works

Example of this theme in action: [Goldsworthy Creations](https://creations.kgol.xyz)

## Required Structure

```yaml
- content
  - news
  - search (required to enable search page)
    - index.html
  - sets
  - works
```

## Post Properties

For each item in 'news', 'sets' or 'works'

- title [string]
- date [datetime]
- draft [bool]
- tags [list]
- sets [list]
- spotlight [bool]
- heroImage [string]
- heroImageBackgroundColor [string]
- galleryitems [list]
- summary [string]
- storeurl [string]
- downloadurl [string]

Example:

```yaml
title: "Braided Tam"
date: 2022-09-15T00:00:00
draft: false
tags:
  [
    "hat",
    "crochet",
  ]
sets: ["tam"]
spotlight: false
heroImage: img/braided_tam_1.jpg # relative to the post's folder
heroImageBackgroundColor: "#a6a09d"
galleryitems:
  [
    "img/braided_tam_1.jpg",
    "img/braided_tam_2.jpg",
  ]
summary: A tam with 6 braids radiating from the center and a pom pom at the top.
storeurl: https://www.ravelry.com/patterns/library/braided-tam---beret
downloadurl: pattern/braided-tam.pdf
```

## Config

An example of what to put in the hugo config menu section

```toml
[menu]
  [[menu.main]]
    name = "About"
    pre = "circle-question-solid"
    url = "/news/about"
    weight = 1
  [[menu.main]]
    name = "Works"
    pre = "yarn-ball"
    url = "/works/"
    weight = 2
  [[menu.main]]
    name = "News"
    pre = "newspaper-regular"
    url = "/news/"
    weight = 3
  [[menu.main]]
    name = "Shop"
    pre = "shop-solid"
    url = "https://www.ravelry.com/patterns/sources/kieran-goldsworthys-ravelry-store"
    weight = 4
  [[menu.main]]
    name = "Search"
    pre = "search"
    url = "/search"
    weight = 5
```

## How to build

A normal dev server:

```bash
hugo server --buildDrafts --buildFuture
```

A dev server with search capabilities:

Note: does not support automatic rebuilding

```bash
hugo --buildDrafts --buildFuture
npx pagefind --source public --serve
```

Build a prod version to publish to the static site host:

```bash
hugo --minify
npx pagefind --source public
```

## Additional Notes

When setting the heroImageBackgroundColor, you might consider putting the hex value of the images average color.
This can be generated at the following site:

https://matkl.github.io/average-color/

https://github.com/matkl
