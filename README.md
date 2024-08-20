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

Add _Bulma 4 Hugo_ either using plain clone or as submodule

- Clone

  ```
  git clone https://github.com/irkode/bulma4hugo.git themes/bulma4hugo
  ```

- Submodule

  ```
  git submodule add https://github.com/irkode/bulma4hugo.git themes/bulma4hugo
  ```

Add the theme to your site configuration

- _Hugo_.yaml

  ```yaml
  theme: bulma4hugo
  # use array syntax if you need other themes, too
  theme:
    - bulma4hugo
    - othertheme
    ...
  ```

- _Hugo_.toml

  ```toml
  theme = "bulma4hugo"
  # use array syntax if you need other themes, too
  theme = ["bulma4hugo", "othertheme", ...]
  ```

## Use _Bulma_

After installing _Bulma 4 Hugo_ you may refer to the _Bulma_ css, sass files from `/assets/bulma`

Just follow the [Official _Bulma_ documentation](https://Bulma.io/).

In general you will use [_Hugo_ Asset Management](https://gohugo.io/categories/asset-management/) to add _Bulma_ to your site.

## Releases

_Bulma 4 Hugo_ follows the _Bulma_ release scheme. So version numbers are same.

New _Bulma_ releases should be added shortly after published.

## Licensing

This is just a repack of _Bulma_. This packer itself is [MIT licensed](./LICENSE)

For _Bulma_ Licensing terms consult the _Bulma_ Documentation at [_Bulma_ Licensing and Copyright](https://github.com/jgthms/bulma#copyright-and-license-)

## Resources

The Bulma CSS framework is (c) by Jeremy Thomas (jgthms)

- [_Bulma_ Homepage](https://bulma.io/)
- [_Bulma_ on GitHub](https://github.com/jgthms/bulma)
