---
layout: post
title:  "My Jekyll journey"
date:   2020-05-09 18:00:00 -0700
categories: jekyll
---
Here are some commands I discovered while troubleshooting things that didn't work for me on Mac when I tried to follow the [GitHub.com Jekyll instructions][github-jekyll-instructions].

At the point where the instructions said to run `bundle exec jekyll VERSION new .` or `jekyll VERSION new .` I couldn't make it work until I found these commands:
```console
gem install jekyll -v 3.8.5
jekyll _3.8.5_ new .
# then edited Gemfile to select jekyll version 3.8.5, github-pages version 204
bundle update
bundle install # updated Gemfile.lock
bundle exec jekyll serve
```

[github-jekyll-instructions]: https://help.github.com/en/github/working-with-github-pages/setting-up-a-github-pages-site-with-jekyll