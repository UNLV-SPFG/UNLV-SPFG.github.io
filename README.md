# UNLV Star & Planet Group Homepage

## Viewing Site Locally
You can [clone](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) this [repo](https://docs.github.com/en/repositories) and build the [GitHub Pages](https://lab.github.com/githubtraining/github-pages) site locally to preview and test any changes, as it can take up to 20 minutes to publish [commits](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/about-commits) to the site after [pushing](https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/making-changes-in-a-branch/pushing-changes-to-github) to [GitHub](https://lab.github.com/githubtraining/introduction-to-github?overlay=register-box-overlay).

### Prerequisites
- [Ruby](https://www.ruby-lang.org/en/documentation/installation/)
- [Jekyll](https://jekyllrb.com/docs/installation/) (`gem install jekyll`)
- [Bundler](https://bundler.io/) (`gem install bundler`)

#### Jekyll on macOS
1. macOS users should first follow [Jekyll's detailed documentation](https://jekyllrb.com/docs/installation/macos/) to ensure proper installation of Ruby.
2. If Bundler was previously installed under a different instance of Ruby, delete it with `gem uninstall bundler`.
3. Reinstall Bundler following the [Local Install subsection](https://jekyllrb.com/docs/installation/macos/#local-install); if you have issues with [Nokogiri](https://nokogiri.org/), try `gem uninstall nokogiri` before installing Bundler (it will fetch the correct version of Nokogiri).

Once the prerequisites have been installed, run the following command in the root of your cloned repo:

`bundle install`

### Build
[Jekyll](https://jekyllrb.com/) is a static site generator, so we need it to build the site before we can view it.
You can run the following command in the root of your local repo to both build and serve it locally:

`bundle exec jekyll serve`

This will run a local web server that you can view at `http://localhost:4000` with your browser.

## Making Changes
- To [contribute to the website](https://docs.github.com/en/get-started/quickstart/contributing-to-projects), you must first [fork](https://docs.github.com/en/get-started/quickstart/contributing-to-projects) this repo, then [commit](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/about-commits) changes to your fork (see subsection topics below), before [making a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) (see our [GitHub wiki guide](https://github.com/UNLV-SPG/technical-resources/wiki/Getting-Started#github) for basic information and additional resources).
- Periodically, and especially before you start making any local changes (to avoid [merge conflicts](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/about-merge-conflicts)), we recommend synchronizing your branch to fetch the latest changes made to this main repo (the _upstream_ branch to your personal fork); see [Syncing your branch](https://github.com/UNLV-SPFG/technical-resources/wiki/Getting-Started#syncing-your-branch) on [our wiki](https://github.com/UNLV-SPFG/technical-resources/wiki) or [Syncing a fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork) at [GitHub Docs](https://docs.github.com/).
- You should make and verify (by [viewing locally](#Viewing-Site-Locally)) changes to the [`dev`](/tree/dev) [branch](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches) of __*your*__ fork and [make a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) _from_ your **head repository: username/UNLV-SPG.github.io, compare: dev** _to_ our **base repository: UNLV-SPG/UNLV-SPG.github.io, base: dev** (see [Creating a pull request from a fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request-from-a-fork) for more information).
- If you're new to Jekyll, we strongly recommend following their < 30-minute [Step by Step Tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/) to understand its core structure and basics.
- For theme _independent_ changes to the site's __content__ or __structure__, see Jekyll's [Docs](https://jekyllrb.com/docs/) by relevant topic.
- This site uses [_Minimal Mistakes_](https://mmistakes.github.io/minimal-mistakes/) as its theme. See the relevant pages under ["Customization"](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) to make modifications. Similarly, for theme _dependent_ __content__ changes, see the relevant pages under ["Content"](https://mmistakes.github.io/minimal-mistakes/docs/posts/).

### Team
To create a new, or modify an existing, [team member](https://unlv-spg.github.io/team/) profile, see the [README.md](/_team/README.md) in the [`_team/`](/_team) diriectory.
### News
To create a new, or modify an existing, [news post](https://unlv-spg.github.io/news/), see the [README.md](/_posts/README.md) in the [`_posts/`](/_posts) diriectory.

### Research
To create a new, or modify an existing, [research page](https://unlv-spg.github.io/research/), see the [README.md](/_research/README.md) in the [`_research/`](/_research) diriectory.
## Issues & Requests
Please create [issues](https://github.com/sabaronett/Zhu-web-page/issues) for any problems identified with the site or requests for changes to the theme or layout.

## Sources
- GitHub Docs: [Working with GitHub Pages](https://docs.github.com/en/github/working-with-github-pages)
- Jekyll: [Step by Step Tutorial](https://jekyllrb.com/docs/step-by-step/01-setup/)
- Minimal Mistakes: [Quick-Start Guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/)
