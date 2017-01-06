# whiteglass

[![Gem Version](https://badge.fury.io/rb/jekyll-whiteglass.svg)](https://badge.fury.io/rb/jekyll-whiteglass)
[![Build Status](https://travis-ci.org/yous/whiteglass.svg?branch=master)](https://travis-ci.org/yous/whiteglass)
[![Dependency Status](https://gemnasium.com/badges/github.com/yous/whiteglass.svg)](https://gemnasium.com/github.com/yous/whiteglass)

Minimal, responsible Jekyll theme for hackers.

## Installation

Add this line to your Jekyll site's Gemfile:

``` ruby
gem "jekyll-whiteglass"
```

And add this line to your Jekyll site's `_config.yml`:

``` yaml
theme: jekyll-whiteglass
```

And then execute:

``` sh
bundle
```

Or install it yourself as:

``` sh
gem install jekyll-whiteglass
```

## Usage

### Customization

To override the default structure and style of whiteglass, simply create the
concerned directory at the root of your site, copy the file you wish to
customize to that directory, and then edit the file. e.g., to override the
[`_includes/head_custom.html`](_includes/head_custom.html) file to specify a
custom style path, create an `_includes` directory, copy
`_includes/head_custom.html` from jekyll-whiteglass gem folder to
`<your-site>/_includes` and start editing that file.

The site's default CSS is in the gem itself,
[`assets/main.scss`](assets/main.scss). To override the default CSS, the file
has to exist at your site source. Do either of the following:

- Create a new instance of `main.scss` at site source
  - Create a new file `main.scss` at `<your-site>/assets/`
  - Add the frontmatter dashes, and
  - Add `@import "whiteglass";`, to `<your-site>/assets/main.scss`
  - Add your custom CSS
- Download the file from this repo
  - Create a new file `main.scss` at `<your-site>/assets/`
  - Copy the contents at [`assets/main.scss`](assets/main.scss) onto the `main.scss` you just created, and edit away
- Copy directly from jekyll-whiteglass gem
  - Go to your local jekyll-whiteglass gem installation directory (run `bundle show jekyll-whiteglass` to get the path to it)
  - Copy the `assets/` folder from there into the root of `<your-site>`
  - Change whatever values you want, inside `<your-site>/assets/main.scss`

### Locale

`site.lang` is used to declare the primary language for each web page within the
site.

`lang: en-US` sets the `lang` attribute for the site to the United States flavor
of English, while `en-GB` would be for the United Kingdom style of English.
Country codes are optional and the shorter variation `lang: en` is also
acceptable. You may want to write a post in different language, then add `lang`
attribute to the frontmatter of that post:

``` yaml
layout: post
title: "안녕하세요"
lang: ko
```

### Description

`site.description` describes the site. This is mainly used in meta descriptions
for improving SEO. Also, you can set `description` attribute for each post:

``` yaml
layout: post
title: Awesome Post
description: This is an awesome post.
```

### Category

Each post can have `categories` attribute. It can be a string or an array. This
will be displayed on index, archive and each post, and provide a link to the
archive of category.

``` yaml
layout: post
title: Awesome Post
categories: Misc
```

``` yaml
layout: post
title: Another Awesome Post
categories:
  - Misc
  - Idea
```

### Metadata for SEO

#### Keywords

Each post can have `keywords` attribute. This is a comma-separated list which is
used in meta descriptions for improving SEO.

``` yaml
layout: post
title: How to configure jekyll-whiteglass
keywords: jekyll, whiteglass, github pages
```

#### Twitter

- `site.twitter_username` sets `twitter:site` and `twitter:creator` meta tag
- `site.twitter_image` sets `twitter:image:src` meta tag
- `page.twitter_card.type` sets `twitter:card` meta tag (default: `summary`)
  - If `page.twitter_card.type` is `gallery`, it sets `twitter:image0`, `twitter:image1`, `twitter:image2` and `twitter:image3` meta tags with `page.twitter_card.image`, `page.twitter_card.image1`, `page.twitter_card.image2` and `page.twitter_card.image3`, respectively
  - If `page.twitter_card.type` is `photo`, `page.twitter_card.width` sets `twitter:image:width` meta tag and `page.twitter_card.height` sets `twitter:image:height` meta tag
- `page.twitter_card.creator` sets `twitter:creator` meta tag. It overrides `site.twitter_username`
- `page.twitter_card.image` sets `twitter:image:src` meta tag if `page.twitter_card.type` is not `gallery`. It overrides `site.twitter_image`

#### Facebook

- `site.facebook_app_id` sets `fb:admins` meta tag
- `site.facebook_page` sets `article:author` meta tag
- `site.facebook_image` sets `og:image` meta tag
- `page.facebook.image` sets `og:image` meta tag. It overrides `site.facebook_image`

### Navigation

To define header links, add titles and URLs under the `main` key in
`_data/navigation.yml`:

``` yaml
main:
  - title: "About"
    url: /about/
  - title: "Archives"
    url: /archives/
  - title: "GitHub"
    url: https://github.com/yous/whiteglass
```

### Enabling Google Analytics

To enable Google Analytics, add the following lines to your Jekyll site:

``` yaml
google_analytics: UA-NNNNNNNN-N
```

## Contributing

Bug reports and pull requests are welcome on GitHub at
<https://github.com/yous/whiteglass>. This project is intended to be a safe,
welcoming space for collaboration, and contributors are expected to adhere to
the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## Development

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run
`bundle exec jekyll serve` and open your browser at
`http://localhost:4000/whiteglass/`. This starts a Jekyll server using your
theme. Add pages, documents, data, etc. like normal to test your theme's
contents. As you make modifications to your theme and to your content, your site
will regenerate and you should see the changes in the browser after a refresh,
just like normal.

## License

The theme is available as open source under the terms of the
[MIT License](http://opensource.org/licenses/MIT).