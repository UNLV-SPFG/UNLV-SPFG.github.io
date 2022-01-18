# News Posts
This folder contains [Markdown](https://www.markdownguide.org/) files for individual posts populating the [**News**](https://unlv-spg.github.io/news/) page.
To create a new post, we recommend copying an existing post as close to the formatting, structure, or features you want and renaming it in the following *hyphenated* format: `YYYY-MM-DD-key-words.md`.

Note:
- Posts can be back- or future-dated, but must use a four-digit year and two-digit month and day.
- `key-words` serve only to differentiate posts with the same date, so keep to a maximum of three (3).
- See [Working with Posts](https://mmistakes.github.io/minimal-mistakes/docs/posts/) for more basic information.
- For post ideas and examples, see this extensive list of *rendered* [Sample Posts](https://mmistakes.github.io/minimal-mistakes/year-archive/) and their corresponding [raw Markdown files](https://github.com/mmistakes/minimal-mistakes/tree/gh-pages-3.1.6/_posts).


## Front Matter
Each file must contain a [YAML](https://yaml.org/) [**front matter**](https://jekyllrb.com/docs/front-matter/) block at the top, sandwiched between triple-dashed lines (`---`), for [Jekyll](https://jekyllrb.com/) to process.
Below is a generic example, followed by a key legend subsection:
```yaml
---
title: "Nature Publication"
last_modified_at: 2016-03-09T18:20:02-08:00
categories:
  - Publications
tags:
  - protoplanetary disks
  - planet formation
  - planetary dynamics
---
```
### Key Legend
- `title:` The title (wrapped in double quotes) to be displayed in the [News list](http://unlv-spg.github.io/news/), at the top of the post's page itself, and in any relevant search results.
- `last_modified_at:` (Optional) The date and time of last modification, formatted as `YYYY-MM-DDTHH:MM:SS-HH:MM`, where the times following `T` is the 24-hour UTC time $\pm$ the [offset](https://en.wikipedia.org/wiki/UTC_offset) (e.g., `-08:00` for PST)
- `categories:` A single term (e.g., `Publications` or `Press`) to categorize your post; see [Posts by Category](http://unlv-spg.github.io/categories/) for an existing list.
- `tags:` Multiple, unlimited entries (each on a separate line) to identify relevant keywords or topics and relate to other tagged posts; see [Posts by Tag](http://unlv-spg.github.io/tags/) for an existing list.
- `[other]:` Posts support additional front matter flags (options) for various features and scenarios; see the Jekyll's documentation on [Posts](https://jekyllrb.com/docs/posts/), and this extensive list of *rendered* [Sample Posts](https://mmistakes.github.io/minimal-mistakes/year-archive/) and their corresponding [raw Markdown files](https://github.com/mmistakes/minimal-mistakes/tree/gh-pages-3.1.6/_posts), for more information.


## Main Content (Markdown)
Jekyll will render your post from any [**Markdown**](https://www.markdownguide.org/) you supply below the [front matter](#Front-Matter) section.
Specifically, our site supports [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/) input, which includes some extensions beyond the standard Markdown specification, notably [_fenced code blocks_](https://github.github.com/gfm/#fenced-code-blocks).
For a GFM reference and more information on Markdown formatting and features, see [Writing on GitHub](https://docs.github.com/en/github/writing-on-github).

For additional post ideas and examples, see this extensive list of *rendered* [Sample Posts](https://mmistakes.github.io/minimal-mistakes/year-archive/) and their corresponding [raw Markdown files](https://github.com/mmistakes/minimal-mistakes/tree/gh-pages-3.1.6/_posts).
