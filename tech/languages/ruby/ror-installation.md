---
title: Ruby on Rails
page: ruby
order: 4
---

# Ruby on Rails installation

## Installing Rails from RubyGems.org

To install Ruby on Rails on Fedora as a gem, install Ruby first together with `ruby-devel`, `gcc`, `libxml2-devel` packages, and then install Rails using the `gem` command:

```
# dnf group install "C Development Tools and Libraries"
# dnf install ruby-devel libxml2-devel
$ gem install rails
```

You might need to install other header files depending on the gems used in your application like installing `sqlite-devel` package for `sqlite3` gem. Note that you can always install the gems from the official repositories as RPM packages to avoid this.

## Installing Rails from Fedora official repositories

To install RPM-packaged Ruby on Rails run:

```
$ sudo dnf install rubygem-rails
```

This will install the framework itself, but if you wish to install all default gems suggested by Rails for new applications, run:

```
$ sudo dnf install rubygem-{rails,sqlite3,coffee-rails,sass-rails,uglifier,jquery-rails,turbolinks,jbuilder,therubyracer,sdoc,spring,byebug,web-console}
```

To take advantage of packaged gems, you need to run `rails` command with `--skip-bundle` option and then run `bundle --local` to lock your dependencies using system gems:

```
$ rails new app --skip-bundle && cd app
$ bundle --local
```
