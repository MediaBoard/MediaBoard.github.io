---
layout: post
title: Biulding a Personal blog in Windows with Jekyll and Github Pages
published: true
---
## Creating a Personal Blog with static Github Pages

material and resources from this URL > https://dfederm.com/creating-a-blog-using-github-pages/

#### Step 1: Prepare the server 

instalar git y ruby

Install Git

* * *

`sudo apt install git`

Install Ruby

* * *

`sudo apt-get install ruby-full build-essential zlib1g-dev`

Ensure RubyGems packages are installed under the user account instead of root.

```
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### Install Jekyll and Bundler:

`gem install jekyll bundler`

install minima gem

`gem install minima`

install jekyll-feed gem

`gem install jekyll-feed`

install jekyll on the github path created

replace Gemfile content with the following:

```
source "https://rubygems.org"

# To update to the latest github dependencies run: `bundle update`
# To list current versions: `bundle exec github-pages versions`
# Check github versions: https://pages.github.com/versions/
gem "github-pages", group: :jekyll_plugins

group :jekyll_plugins do
  gem 'jekyll-feed'
  gem 'jekyll-paginate'
  gem 'jekyll-seo-tag'
  gem 'jekyll-sitemap'
end

# Windows and JRuby does not include zoneinfo files, so bundle the tzinfo-data gem
# and associated library.
install_if -> { RUBY_PLATFORM =~ %r!mingw|mswin|java! } do
  gem "tzinfo", "~> 1.2"
  gem "tzinfo-data"
end

# Performance-booster for watching directories on Windows
gem "wdm", "~> 0.1.1", :install_if => Gem.win_platform?
```

To build the site and serve it locally, run:

`bundle exec jekyll serve --drafts --livereload`

Enter text in [Markdown](http://daringfireball.net/projects/markdown/). Use the toolbar above, or click the **?** button for formatting help.
