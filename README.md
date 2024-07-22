# **Bulma4Hugo** - Use _Bulma_ easily within your _Hugo_ site

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

If you have problems/issues with _Bulma_ itself, please use the [_Bulma_ issue tracker](https://github.com/jgthms/_Bulma_/issues).

Anything regarding packaging may be addressed here [Bulma4Hugo](https://github.com/irkode/Bulma4Hugo)

## Use Bulma4Hugo in your _Hugo_ project

Set up a you _Hugo_ site and `cd` to site root folder.

Add **Bulma\_ 4 \_Hugo** to your site using one of the below methods

### _Hugo_ module (preferred)

- First [install Go](https://go.dev/doc/install) (needed for _Hugo_ modules)

- add the module to your site config file:

  - _Hugo_.yaml

    ```yaml
    module:
      imports:
        - path: github.com/irkode/Bulma4Hugo
    ```

  - _Hugo_.toml

    ```toml
    [module]
      [module.imports]
        path = github.com/irkode/Bulma4Hugo
    ```

### Git

In your site root folder choose the method you want

- Clone

  ```
  git clone https://github.com/irkode/Bulma4Hugo.git themes/Bulma4Hugo
  ```

- Submodule

  ```
  git submodule add https://github.com/irkode/Bulma4Hugo.git themes/Bulma4Hugo
  ```

Add the Theme to your site configuration

- _Hugo_.yaml

  ```yaml
  theme: Bulma4Hugo
  # use array syntax if you need other themes, too
  theme:
    - Bulma4Hugo
    - othertheme
    ...
  ```

- _Hugo_.toml

  ```toml
  theme = "Bulma4Hugo"
  # use array syntax if you need other themes, too
  theme = ["Bulma4Hugo", "othertheme", ...]
  ```

## Use _Bulma_

After installing Bulma4Hugo you may refer to the _Bulma_ css, sass files using `/assets/_Bulma_`

Just follow the [Official _Bulma_ documentation](https://_Bulma_.io/).

In general you will use [_Hugo_ Asset Management](https://go_Hugo_.io/categories/asset-management/) to add _Bulma_ tzo your site.

## Releases

**Bulma\_ 4 \_Hugo** follows the _Bulma_ release scheme. So version numbers are same.

Only tagged releases are available.

New _Bulma_ releases should be added shortly after published.

## Licensing

This is just a repack of _Bulma_. The packer itself is [MIT licensed](./LICENSE)

For _Bulma_ Licensing terms consult the _Bulma_ Documentation at [_Bulma_ Licensing and Copyright](https://github.com/jgthms/_Bulma_#copyright-and-license-)
