---
layout: post
title:  "My Jekyll journey"
date:   2020-05-09 18:00:00 -0700
categories: jekyll
---
<i>UPDATE February 13, 2022: Bumped jekyll and github-pages versions.</i>

Here are some workarounds I discovered while troubleshooting things that didn't work for me on Mac when I tried to follow the [GitHub.com Jekyll instructions][github-jekyll-instructions]. Jekyll is a blog site generator that works with GitHub Pages to create and host a free blog at https://<i>your-github-accountname</i>.github.io

At the point where the instructions said to run `bundle exec jekyll VERSION new .` or `jekyll VERSION new .` I couldn't make those work until I found these commands:
```shell
gem install jekyll -v 3.9.0
jekyll _3.9.0_ new .
# then edited Gemfile to select jekyll version 3.9.0, github-pages version 223
bundle update
bundle install # updated Gemfile.lock
# after that I could serve the site locally with the following command
bundle exec jekyll serve
# but note that you need to stop (ctrl-C) and restart for any changes to _config.yml to take effect
```
(I found the jekyll and github-pages versions here: [GitHub Pages Dependency versions][github-pages-dependency-versions].)

Next I put everything in the docs folder (in the master branch), following GitHub's instructions, but then [my site][my-site] returned 404 - GitHub couldn't find anything. I fixed it by moving the files from the docs folder to the repository root folder. I guessed this solution because the repository settings page says "User pages must be built from the master branch." I didn't see [the choices listed here][github-pages-choosing-a-publishing-source].

Finally, I changed the Jekyll markdown in \_config.yml to GFM (GitHub flavored markdown), because then blog pages are rendered nicely in GitHub's web view, like this page: https://github.com/sorenlassen/sorenlassen.github.io/blob/master/_posts/2020-05-09-my-jekyll-journey.md

[github-jekyll-instructions]: https://help.github.com/en/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll
[github-pages-choosing-a-publishing-source]: https://help.github.com/en/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#choosing-a-publishing-source
[my-site]: https://sorenlassen.github.io/
[github-pages-dependency-versions]: https://pages.github.com/versions/
