# UNLV Star & Planet Group Homepage

## Viewing Site Locally
You can [clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this [repo](https://docs.github.com/en/repositories) and build the [GitHub Pages](https://lab.github.com/githubtraining/github-pages) site locally to preview and test any changes, as it can take up to 20 minutes to publish [commits](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/about-commits) to the site after [pushing](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/pushing-changes-to-github) to [GitHub](https://lab.github.com/githubtraining/introduction-to-github?overlay=register-box-overlay).

### Prerequisites
- [Ruby](https://www.ruby-lang.org/en/documentation/installation/)
- [Jekyll](https://jekyllrb.com/docs/installation/) (`$ gem install jekyll`)
- [Bundler](https://bundler.io/) (`$ gem install bundler`)

Once the prerequisites have been installed, run the following command in the root of your cloned repo:

`$ bundle install`

### Build
[Jekyll](https://jekyllrb.com/) is a static site generator, so we need it to build the site before we can view it.
You can run the following command in the root of your local repo to both build and serve it locally:

`$ bundle exec jekyll serve`

This will run a local web server that you can view at `http://localhost:4000` with your browser.

## Making Changes
If you're new to Jekyll, we strongly recommend following their < 30-minute [Step by Step Tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/) to understand its core structure and basics.

For theme _independent_ changes to the site's __content__ or __structure__, see Jekyll's [Docs](https://jekyllrb.com/docs/) by relevant topic.

This site uses [_Minimal Mistakes_](https://mmistakes.github.io/minimal-mistakes/) as its theme. See the relevant pages under ["Customization"](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) to make modifications. Similarly, for theme _dependent_ __content__ changes, see the relevant pages under ["Content"](https://mmistakes.github.io/minimal-mistakes/docs/posts/).

## Issues & Requests
Please create [issues](https://github.com/sabaronett/Zhu-web-page/issues) for any problems identified with the site or requests for changes to the theme or layout.

## Sources
- GitHub Docs: [Working with GitHub Pages](https://docs.github.com/en/github/working-with-github-pages)
- Jekyll: [Step by Step Tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/)
- Minimal Mistakes: [Quick-Start Guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)