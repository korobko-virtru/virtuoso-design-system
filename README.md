# Virtuoso Design System
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-10-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

This repo enables using the Virtuoso Design System as front-end code (HTML, CSS, & JavaScript).

[Dive into the docs.](https://avkvirtru.github.io/virtuoso-design-system/)

## Docs

The documentation for Virtuoso is [hosted on GitHub Pages](https://avkvirtru.github.io/virtuoso-design-system/) and powered by [Storybook](https://storybook.js.org). 

To run storybook locally:

```shell
npm run storybook
```





## Design Tokens

> Design tokens are the visual design atoms of the design system — specifically, they are named entities that store visual design attributes. We use them in place of hard-coded values (such as hex values for color or pixel values for spacing) in order to maintain a scalable and consistent visual system for UI development.
>
> — [Salesforce Lightning Design System](https://www.lightningdesignsystem.com/design-tokens/)

[Style Dictionary](https://amzn.github.io/style-dictionary/#/) is a build system that allows you to define **design tokens** once, in a way for any platform or language to consume. 

1. Our design tokens are defined in `lib/styles/style_dict/tokens/` as JSON files…

1. …read by the config in `lib/styles/style_dict/config.json`

1. …and built by the command 
```shell
npm run style-dictionary:build
```

1. …which creates `lib/styles/build/` files for CSS, JS, or whatever platform needs them.

1. You can clear the built tokens with 
```shell
npm run style-dictionary:clean
```





## Examples

Examples can be found in `/examples`





## Releasing

Releases are handled by [Auto](https://intuit.github.io/auto/). 

1. Please tag your PRs "release" in order for Auto to find them.

2. Then, all you have to do is `npm run release` and you'll get:

  * automatic changelog
  * bump npm version
  * publish to npm — based on your `npm login` or NPM_TOKEN in `.env`
  * make a GitHub release — based on your GH_TOKEN in `.env`

This works with the magic described in [auto shipit docs](https://intuit.github.io/auto/docs/generated/shipit).

A static version of the Storybook docs are generated automatically before we publish releases to npm. 





## Development &  Testing

To develop new components make sure to:

- add components to `/lib/components`
- add helpers and hooks to `/lib/helpers`
- add relevant stories to `/stories`
- add tests next to the component

**Run locally**

```shell
npm run storybook
```

**Run tests**

```shell
npm run test
```





## Visual Regression Testing (VRT)

This repository uses Loki for VRT to ensure the visual appearance of states of the components does not regress. Baseline reference images are intentionally checked into this repository in `.loki/reference/`.

### Running VRT locally

You can run the VRT tests locally to check to see if your changes have caused visual regressions from the existing baselines for *all components* based on the `loki` config in **package.json**:

```shell
npm run test:vrt
```

For faster results, you can run a subset of tests using `--storiesFilter`: 

```shell
npm run test:vrt -- --storiesFilter=Input
```

Any failed tests will be output in `.loki/difference/`. You can inspect any visual differences that are highlighted in these output images.

If the differences are intended, you can update the baselines by following the instructions in the next section.

### Updating Loki Baselines

_Note_: Before performing this step, you must first run the VRT once (see previous section).

If you run the tests above and have legitimate changes in the visual appearance of the components, you can approve new baselines, which will replace the existing baseline images with the new, current images:

```shell
npx loki approve
```

This will immediately take all new baseline images from the last test run and replace the existing baseline images. If you wish to update a specific test case image only but reject other changes, see the [Loki CLI reference](https://loki.js.org/command-line-arguments.html).

We recommend only approving new baselines once all unintended visual changes have been fixed, then running the command above so no fine-grained filtering of new baselines is needed.

---

Copyright © 2020 Virtru Corporation

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://linkedin.com/in/jrschumacher"><img src="https://avatars1.githubusercontent.com/u/46549?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Ryan Schumacher</b></sub></a><br /><a href="https://github.com/virtru/virtuoso-design-system/commits?author=jrschumacher" title="Code">💻</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=jrschumacher" title="Documentation">📖</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=jrschumacher" title="Tests">⚠️</a></td>
    <td align="center"><a href="https://avk.github.io/"><img src="https://avatars0.githubusercontent.com/u/44370126?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Arthur Klepchukov</b></sub></a><br /><a href="https://github.com/virtru/virtuoso-design-system/commits?author=avkvirtru" title="Code">💻</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=avkvirtru" title="Documentation">📖</a></td>
    <td align="center"><a href="https://github.com/kuguarpwnz"><img src="https://avatars0.githubusercontent.com/u/6388788?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Vlad Baranchuk</b></sub></a><br /><a href="https://github.com/virtru/virtuoso-design-system/commits?author=kuguarpwnz" title="Code">💻</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=kuguarpwnz" title="Documentation">📖</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=kuguarpwnz" title="Tests">⚠️</a></td>
    <td align="center"><a href="https://github.com/shawyu"><img src="https://avatars1.githubusercontent.com/u/38223448?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Shaw Yu</b></sub></a><br /><a href="https://github.com/virtru/virtuoso-design-system/commits?author=svirtryu" title="Code">💻</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=svirtryu" title="Documentation">📖</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=svirtryu" title="Tests">⚠️</a></td>
    <td align="center"><a href="https://twitter.com/nathanab_"><img src="https://avatars0.githubusercontent.com/u/3252545?v=4?s=100" width="100px;" alt=""/><br /><sub><b>NathanAB</b></sub></a><br /><a href="https://github.com/virtru/virtuoso-design-system/commits?author=NathanAB" title="Code">💻</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=NathanAB" title="Documentation">📖</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=NathanAB" title="Tests">⚠️</a></td>
    <td align="center"><a href="http://alwaysmorehats.com/"><img src="https://avatars1.githubusercontent.com/u/1030358?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Stephen Smith</b></sub></a><br /><a href="https://github.com/virtru/virtuoso-design-system/commits?author=AlwaysMoreHats" title="Code">💻</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=AlwaysMoreHats" title="Documentation">📖</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=AlwaysMoreHats" title="Tests">⚠️</a></td>
    <td align="center"><a href="https://github.com/sergeyd-virtru"><img src="https://avatars2.githubusercontent.com/u/41566731?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Sergey Diniovskiy</b></sub></a><br /><a href="https://github.com/virtru/virtuoso-design-system/commits?author=sergeyd-virtru" title="Code">💻</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=sergeyd-virtru" title="Documentation">📖</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=sergeyd-virtru" title="Tests">⚠️</a></td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/Nnamdi101"><img src="https://avatars1.githubusercontent.com/u/17769444?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Nnamdi101</b></sub></a><br /><a href="https://github.com/virtru/virtuoso-design-system/commits?author=Nnamdi101" title="Code">💻</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=Nnamdi101" title="Documentation">📖</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=Nnamdi101" title="Tests">⚠️</a></td>
    <td align="center"><a href="https://github.com/ivanovSPvirtru"><img src="https://avatars3.githubusercontent.com/u/41641307?v=4?s=100" width="100px;" alt=""/><br /><sub><b>ivanovSPvirtru</b></sub></a><br /><a href="https://github.com/virtru/virtuoso-design-system/commits?author=ivanovSPvirtru" title="Code">💻</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=ivanovSPvirtru" title="Documentation">📖</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=ivanovSPvirtru" title="Tests">⚠️</a></td>
    <td align="center"><a href="https://github.com/suchak1"><img src="https://avatars1.githubusercontent.com/u/42231639?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Krish Suchak</b></sub></a><br /><a href="https://github.com/virtru/virtuoso-design-system/commits?author=suchak1" title="Code">💻</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=suchak1" title="Documentation">📖</a> <a href="https://github.com/virtru/virtuoso-design-system/commits?author=suchak1" title="Tests">⚠️</a></td>
  </tr>
</table>

<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!