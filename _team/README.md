# Team Members
This folder contains [Markdown](https://www.markdownguide.org/) files for the individual members populating the [**Team**](https://unlv-spg.github.io/team/) page.
To create your own, we recommend copying an existing member profile as close to the structure you want (e.g., a simple paragraph or multiple, extensive sections) and renaming it as your `firstname-lastname.md`.


## Front Matter
Each file must contain a [YAML](https://yaml.org/) [**front matter**](https://jekyllrb.com/docs/front-matter/) block at the top, sandwiched between triple-dashed lines (`---`), for [Jekyll](https://jekyllrb.com/) to process.
Below is a generic example, followed by a key legend subsection:
```yaml
---
title: "[display name]"
excerpt: "[position]"
header:
  teaser: /assets/images/team/[firstname-lastname].jpg
sidebar:
  - title: "Position"
    image: /assets/images/team/[firstname-lastname].jpg
    text: "[title]"
  - title: "Research Interests"
    text: "<ul>
    <li> [Topic 1]
    <li> [Topic 2]"
---
```
### Key Legend
- `title:` Your name (wrapped in double quotes) to be displayed in the team directory and on the top header of your profile page, e.g., `"Edwin P. Hubble"`; matching your Markdown filename is **not** required (e.g., can include a middle initial and non-Latin characters).
- `excerpt:` Your position (wrapped in double quotes) as one of the following _fixed_ values:
  - `"Principal Investigator"`
  - `"Postdoctoral Scholar"`
  - `"Graduate Assistant"`
  - `"Alum"`
- `header:`
  - `teaser:` The path to your profile image (`.jpg` or `.png`) in [`/assets/images/team/`](https://github.com/UNLV-SPG/UNLV-SPG.github.io/tree/dev/assets/images/team) to appear on the [main directory](https://unlv-spg.github.io/team/); please crop your photo to have *square* dimensions (i.e., 1:1 aspect ratio) and match its filename to that of your Markdown file (e.g., `firstname-lastname.jpg`).
- `sidebar:`
  - `title: "Position"` Leave as is.
  - `image:` The same path to your profile image to appear on your profile sidebar; see `header:`, `teaser:` above for the standard path and image format.
  - `text:` Your position (wrapped in double quotes); see `excerpt:` above for valid fixed values.
  - `title: "Research Interests"` (Optional) To be included on your profile sidebar.
  - `text: "<ul>` (HTML for _**u**nnumbered **l**ist_) List each item on a separate line prepended with `<li> ` (HTML for _**l**ist **i**tem_, ensuring a single empty space before your text); best to keep to a maximum of 2-3 words and must include a double quote (`"`) after the final item; see [example above](#Front-Matter)


## Main Content (Markdown)
Jekyll will render your profile from any [**Markdown**](https://www.markdownguide.org/) you supply below the [front matter](#Front-Matter) section.
Specifically, our site supports [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/) input, which includes some extensions beyond the standard Markdown specification, notably [_fenced code blocks_](https://github.github.com/gfm/#fenced-code-blocks).
For a GFM reference and more information on Markdown formatting and features, see [Writing on GitHub](https://docs.github.com/en/github/writing-on-github).
