## Table of contents

- [Getting Started](#getting-started)
- [Loading from CDN](#loading-from-cdn)
- [Documentation](#documentation)


## Getting Started

There are a couple of options available for including NC State Bootstrap in your project:

- Load resources from the NC State CDN
- Install with [npm](https://www.npmjs.com/): `npm install git+ssh://git@github.ncsu.edu:ncstate-ucomm/ncstate-bootstrap.git` (more info at <https://github.ncsu.edu/ncstate-ucomm/demo-npm-bootstrap>)


## Loading from CDN

All Bootstrap CSS and JS files are available on the NC State CDN at `https://cdn.ncsu.edu/brand-assets/bootstrap-4/`.

### What's included

Within the Bootstrap 4 directory of the CDN you'll find the following directories and files.

```
bootstrap-4/
├── css/
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css
│   ├── bootstrap.min.css.map
│   ├── bootstrap-grid.css
│   ├── bootstrap-grid.css.map
│   ├── bootstrap-grid.min.css
│   ├── bootstrap-grid.min.css.map
│   ├── bootstrap-reboot.css
│   ├── bootstrap-reboot.css.map
│   ├── bootstrap-reboot.min.css
│   └── bootstrap-reboot.min.css.map
└── js/
    ├── bootstrap.bundle.js
    ├── bootstrap.bundle.min.js
    ├── bootstrap.js
    └── bootstrap.min.js
```

We provide compiled CSS and JS (`bootstrap.*`), as well as compiled and minified CSS and JS (`bootstrap.min.*`). CSS [source maps](https://developers.google.com/web/tools/chrome-devtools/debug/readability/source-maps) (`bootstrap.*.map`) are available for use with certain browsers' developer tools. Bundled JS files (`bootstrap.bundle.js` and minified `bootstrap.bundle.min.js`) include [Popper](https://popper.js.org/), but not [jQuery](https://jquery.com/).

### Starter Template

When loading all Bootstrap resources from the CDN, your page should look something like this:

````html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://cdn.ncsu.edu/brand-assets/bootstrap-4/css/bootstrap.min.css">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.0/umd/popper.min.js" integrity="sha384-cs/chFZiN24E4KMATLdqdvsezGxaGsi4hLGOzlXwp5UZB1LY//20VyM2taTB4QvJ" crossorigin="anonymous"></script>
    <script src="https://cdn.ncsu.edu/brand-assets/bootstrap-4/js/bootstrap.min.js"></script>
  </body>
</html>
````

## Documentation

Bootstrap's documentation is built with [Jekyll](https://jekyllrb.com/). We are unable to easily override the contents of the stock Bootstrap documentation, so a fully customized copy of the docs is not available. However, because our customizations are purely stylistic, you can still use the [official documentation](https://getbootstrap.com/). Anywhere the official docs reference a resource (i.e., a CSS or JS file), just remember to use ours instead.

While the [official docs](https://getbootstrap.com/) should be your primary source of information, we do provide a subset of that documentation to demonstrate the visual style of our flavor. You can view branded copies of the content and components sections of the documentation at <https://brand.ncsu.edu/bootstrap/v4>.

### Running documentation locally

1. [Download and install Node.js](https://nodejs.org/download/).
2. Run `npm install` to install Node.js dependencies.
3. [Install Ruby](https://www.ruby-lang.org/en/documentation/installation/), install [Bundler](https://bundler.io/) with `gem install bundler`, and finally run `bundle install`.
4. Run `npm run dist` to rebuild distributed CSS and JavaScript files.
5. Run `npm run docs` to rebuild the branded docs.
6. Docs are now available in the `_gh_pages` directory.
