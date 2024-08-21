# **Bulma 4 Hugo** - Use _Bulma_ easily within your _Hugo_ site

_Bulma_ releases packaged for use with _Hugo_ as module or using git.

## Features

- access to all build variants from _Bulma_ release.
- choose a precompiled CSS variant
- use the SASS and your build pipeline
  - customize SASS if you want
- easy version change (depending on your chosen usage)

## Disclaimer

This is a brute force repacking of _Bulma_ release to ease up adding it to a _Hugo_ site.

- There's no stuff like verification and testing.
- delivered as-is, no guarantee no warranty
- No _Bulma_ support here

## Support

If you have problems/issues with _Bulma_ itself, please use the [_Bulma_ issue tracker](https://github.com/jgthms/bulma/issues).

Anything regarding packaging may be addressed here [Bulma 4 Hugo](https://github.com/irkode/bulma4hugo)

## Use _Bulma 4 Hugo_ in your _Hugo_ project

Set up a your _Hugo_ site and `cd` to site root folder.

Now add _Bulma 4 Hugo_ to your site using one of the below methods

### _Hugo_ module (preferred)

- First [install Go](https://go.dev/doc/install) (needed for _Hugo_ modules)

- initialize your _Hugo_ site as module

  `hugo mod init your_module`

- add the module to your site config file:

  - _Hugo_.yaml

    ```yaml
    module:
      imports:
        - path: github.com/irkode/bulma4hugo
    ```

  - _Hugo_.toml

    ```toml
    [module]
      [[module.imports]]
        path = "github.com/irkode/bulma4hugo"
    ```

### Git

Add _Bulma 4 Hugo_ either using plain clone or as submodule.

> HINT: we have no branches for the _Bulma_ releases, just _tags_:
>
> Example: release `0.7.5` is tagged as `v0.7.5`

- Clone

  ```
  git clone --depth 1 --branch v0.7.5 https://github.com/irkode/bulma4hugo.git themes/bulma4hugo
  ```

- Submodule

  To use a git submodule you must ofc hava a git repository for your site. If your's is not `git init .`

  It's not possible add a submodule using a tag. so you will have to something like:

  ```
  git submodule add https://github.com/irkode/bulma4hugo.git themes/bulma4hugo
  cd themes/bulma4hugo
  git checkout v0.7.5
  cd ../..
  git add themes/bulma4hugo
  git commit -m "bumped Bulma 4 Hugo to release 0.7.5"
  ```

Add the theme to your site configuration

- _Hugo_.yaml

  ```yaml
  theme: bulma4hugo
  ```

- _Hugo_.toml

  ```toml
  theme = "bulma4hugo"
  ```

## Use _Bulma_

After installing _Bulma 4 Hugo_ you may refer to the _Bulma_ css, sass files from `/assets/bulma`

Just follow the [Official _Bulma_ documentation](https://Bulma.io/).

In general you will use [_Hugo_ Asset Management](https://gohugo.io/categories/asset-management/) to add _Bulma_ to your site.

### Files provided in different versions

Different releases of bulma provide different css/sass files to include

- pre 0.6.x versions just provide `css/bulma.css`, `bulma.sass`

- with 7.0 a minified CSS is provided `css/bulma.min.css`

- later versions may add more stuff

Since `Bulma 4 Hugo 0.7.6` we list the provided files in our release notes. For more details on a release consult the bulma release notes.

> keep in mind that we mount _Bulma_ to `assets/bulma` folder, so you will have to add a leading `bulma`. See examples below.

### Examples

- use the (minified) css file

- use as any other global resource [resources.Get](https://gohugo.io/functions/resources/get/)

  ```shell
  {{ with resources.Get "bulma/css/bulma.min.css" }}
     <link rel="stylesheet" href="{{ .RelPermalink }}" integrity="{{ .Data.Integrity }}" crossorigin="anonymous" />
  {{ end }}
  ```

- use the sass file

  Straight from the docs at: [Asset Management - SASS](https://gohugo.io/hugo-pipes/transpile-sass-to-css/)

  ```
  {{ with resources.Get "bulma/bulma.scss" | toCSS | minify | fingerprint }}
     <link rel="stylesheet" href="{{ .RelPermalink }}" integrity="{{ .Data.Integrity }}" crossorigin="anonymous">
  {{ end }}
  ```

## Release versioning

_Bulma 4 Hugo_ follows the _Bulma_ release scheme. So version numbers are same.

New _Bulma_ releases should be added shortly after published.

## Licensing

This is just a repack of _Bulma_. This packer itself is [MIT licensed](./LICENSE)

For _Bulma_ Licensing terms consult the _Bulma_ Documentation at [_Bulma_ Licensing and Copyright](https://github.com/jgthms/bulma#copyright-and-license-)

## Resources

The Bulma CSS framework is (c) by Jeremy Thomas (jgthms)

- [_Bulma_ Homepage](https://bulma.io/)
- [_Bulma_ on GitHub](https://github.com/jgthms/bulma)
