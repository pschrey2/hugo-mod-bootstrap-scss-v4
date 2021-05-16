## IMPORTANT

Personal fork. When doing the pull request to master, update the path back to github.com/`gohugoio`/hugo-mod-bootstrap-scss-v4 in two places:

1. This `README.md` file under section Use.
2. The first line in the `go.mod` file.

---

This is a [Hugo module](https://gohugo.io/hugo-modules/) that packages the [Bootstrap v4](https://getbootstrap.com/docs/4.6/getting-started/introduction/) SCSS source ready to be used in Hugo.

You need the Hugo extended version and [Go](https://golang.org/dl/) to use this component.

## Use

Add the component either to your Hugo site's config or to your Hugo theme's config.

1. Hugo site's config:

   ```toml
   [module]
   [[module.imports]]
   path = "github.com/pschrey2/hugo-mod-bootstrap-scss-v4"
   ```

2. Hugo theme's config:

   ```toml
   [module]
   [[module.mounts]]
   # Workaround for https://github.com/gohugoio/hugo/issues/6945
   source = "assets/scss/bootstrap/_vendor"
   target = "assets/scss/bootstrap/vendor"
   [[module.imports]]
   path = "github.com/pschrey2/hugo-mod-bootstrap-scss-v4"
   [[module.imports.mounts]]
   source = "assets/scss/bootstrap"
   target = "assets/scss/bootstrap"
   ```

If added to a theme, the workaround requires also a local copy the `_rfs.scss` file in the `assets/scss/bootstrap/_vendor` folder.

The Bootstrap SCSS will be mounted in `assets/scss/bootstrap`, so you can then import either all:

```scss
@import "bootstrap/bootstrap";
```

Or only what you need:


```scss
@import "bootstrap/functions";
@import "bootstrap/variables";
@import "bootstrap/mixins";
@import "bootstrap/root";
@import "bootstrap/reboot";
@import "bootstrap/type";
@import "bootstrap/images";
@import "bootstrap/code";
@import "bootstrap/grid";
@import "bootstrap/tables";
@import "bootstrap/forms";
@import "bootstrap/buttons";
@import "bootstrap/transitions";
@import "bootstrap/dropdown";
@import "bootstrap/button-group";
@import "bootstrap/input-group";
@import "bootstrap/custom-forms";
@import "bootstrap/nav";
@import "bootstrap/navbar";
@import "bootstrap/card";
@import "bootstrap/breadcrumb";
@import "bootstrap/pagination";
@import "bootstrap/badge";
@import "bootstrap/jumbotron";
@import "bootstrap/alert";
@import "bootstrap/progress";
@import "bootstrap/media";
@import "bootstrap/list-group";
@import "bootstrap/close";
@import "bootstrap/toasts";
@import "bootstrap/modal";
@import "bootstrap/tooltip";
@import "bootstrap/popover";
@import "bootstrap/carousel";
@import "bootstrap/spinners";
@import "bootstrap/utilities";
@import "bootstrap/print";
```


## Versions

This repository will be versioned following the minor and patch versions in the v4 series of Bootstrap.
