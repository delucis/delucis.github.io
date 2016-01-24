# Installation

The following steps are for OS X. Skip steps if something is already installed,
though updating/checking versions is probably advisable.

## Environment Set-Up

### Make sure you have [a user version of Ruby installed](http://jekyllrb.com/docs/troubleshooting/#jekyll-amp-mac-os-x-1011)

```sh
brew install ruby
export PATH=/usr/local/bin:$PATH
```

The first line installs Ruby via [Homebrew](http://brew.sh/).  
The second line updates the `$PATH` to use the Homebrew copy of Ruby ahead of
OS X’s system copy.

### Install ImageMagick

```sh
brew install ImageMagick
```

Used for
[`jekyll-picture-tag`](https://github.com/robwierzbowski/jekyll-picture-tag)
image processing.

### Install [Bundler](http://bundler.io/)

```sh
gem install bundler
```

Bundler will handle dependencies for the repository.

## Repository Set-Up

### Download repo

`cd` to the directory where you want to clone the repo, then do:

```sh
git clone https://github.com/delucis/v3.chrisswithinbank.net.git
cd v3.chrisswithinbank.net
```

### Install dependencies

```sh
bundle install
```

Bundler will read the repository’s [`Gemfile`](Gemfile) and install listed
dependencies.

## Running local server and building

```sh
bundle exec jekyll serve
```

This will attempt to build the site and serve to <http://0.0.0.0:4000/>.

The site files are built to `_site/`.

To build without serving locally do:

```sh
bundle exec jekyll build
```

## Troubleshooting

There are sometimes build problems with the
[`jekyll-sitemap`](https://github.com/jekyll/jekyll-sitemap)
plug-in. To try building without `jekyll-sitemap` activated, remove the
relevant line from the `gems` item in [`config.yml`](config.yml):

```yml
gems:
    - jekyll-sitemap
    - jekyll-feed
    - jekyll-picture-tag
    - jekyll-last-modified-at
```

After a successful initial build, replacing that line restores full
functionality, and usually leads to non-failing subsequent builds.