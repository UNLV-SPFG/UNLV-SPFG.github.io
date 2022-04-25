# Team Members
This folder contains [Markdown](https://www.markdownguide.org/) files for the individual members populating the [**Team**](https://unlv-spfg.github.io/team/) page.
To create your own, we recommend copying an existing member profile as close to the structure you want (e.g., a simple paragraph or multiple, extensive sections) and renaming it as your `lastname-firstname.md`.


## Front Matter
Each file must contain a [YAML](https://yaml.org/) [**front matter**](https://jekyllrb.com/docs/front-matter/) block at the top, sandwiched between triple-dashed lines (`---`), for [Jekyll](https://jekyllrb.com/) to process.
Below is a generic example, followed by a key legend subsection:
```yaml
---
title: "Lastname, Firstname"
excerpt: "[position]"
header:
  teaser: /assets/images/team/lastname-firstname.jpg
sidebar:
  - title: "Position"
    image: /assets/images/team/lastname-firstname.jpg
    text: "[position]<br>
    <a href='mailto:user@domain.org'>
      <i class='fas fa-fw fa-envelope'></i>Email</a><br>
    <a href='https://github.com/username' target='_blank'
      <i class='fab fa-fw fa-github'></i>GitHub</a><br>
    <a href='https://scholar.google.com/citations?user=ID' target='_blank'>
      <i class='fas fa-fw fa-user-graduate'></i>Google Scholar</a><br>
    <a href='/tags/#firstname-lastname'>
      <i class='fas fa-fw fa-newspaper'></i>News</a><br>
    <a href='https://orcid.org/0000-0000-0000-0000' target='_blank'>
      <i class='fab fa-fw fa-orcid'></i>ORCiD</a>"
  - title: "Research Interests"
    text: "<ul>
    <li> Topic 1
    <li> Topic 2"
---
```
### Key Legend
- `title:` Your name—last name *first*, immediately followed by a comma (`,`), and wrapped in double quotes—to be displayed in the team directory and on the top header of your profile page, e.g., `"Hubble, Edwin P."`; you can include a middle initial.
- `excerpt:` Your position (wrapped in double quotes) as one of the following _fixed_ values:
  - `"Principal Investigator"`
  - `"Postdoctoral Scholar"`
  - `"Graduate Assistant"`
  - `"Alum"`
- `header:`
  - `teaser:` The path to your profile image (`.jpg` or `.png`) in [`/assets/images/team/`](https://github.com/UNLV-SPFG/UNLV-SPFG.github.io/tree/dev/assets/images/team) to appear on the [main directory](https://unlv-spfg.github.io/team/); please crop your photo to have *square* dimensions (i.e., 1:1 aspect ratio) and match its filename to that of your Markdown file (e.g., `lastname-firstname.jpg`).
- `sidebar:`
  - `title: "Position"` Leave as is.
    - `image:` The same path to your profile image to appear on your profile sidebar; see `header:`, `teaser:` above for the standard path and image format.
    - `text:` Your position (see `excerpt:` above for valid fixed values), followed by any optional personal links; use the sample HTML link and icon tags in the example above, making sure to wrap your hypertext reference (`href=`) in *single* quotes (`'`); you must include a `"` (double quote) after the final item; see [example above](#Front-Matter).
  - `title: "Research Interests"` (Optional) To be included on your profile sidebar.
    - `text: "<ul>` (HTML for _**u**nnumbered **l**ist_) (Optional) List each item on a separate line prepended with `<li> ` (HTML for _**l**ist **i**tem_, ensuring a single empty space before your text); best to keep to a maximum of 2-3 words and must include a double quote (`"`) after the final item; see [example above](#Front-Matter).


## Main Content (Markdown)
Jekyll will render your post from any [**Markdown**](https://www.markdownguide.org/) you supply below the [front matter](#Front-Matter) section.
Specifically, our site supports [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/) input, which includes some extensions beyond the standard Markdown specification, notably [_fenced code blocks_](https://github.github.com/gfm/#fenced-code-blocks).

- For a GFM reference and more information on Markdown formatting and features, see [Writing on GitHub](https://docs.github.com/en/github/writing-on-github).
- For additional post ideas and examples, see this extensive list of *rendered* [Sample Posts](https://mmistakes.github.io/minimal-mistakes/year-archive/) and their corresponding [raw Markdown files](https://github.com/mmistakes/minimal-mistakes/tree/gh-pages-3.1.6/_posts).
- See also [GitHub Learning Lab's](https://lab.github.com/), 10 step, 45 min course on [Communicating using Markdown](https://lab.github.com/githubtraining/communicating-using-markdown).
