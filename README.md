<p align="center">
  <h3 align="center">Basic template for Mono Repo</h3>

  <p align="center">
    <br />
    <a href="https://github.com/gagoar/ts-monorepo-template#table-of-contents"><strong>Explore the docs »</strong></a>
    <br />
    <a href="https://github.com/gagoar/ts-monorepo-template/issues">Report Bug</a>
    ·
    <a href="https://github.com/gagoar/ts-monorepo-template/issues">Request Feature</a>
  </p>
</p>

## Table of Contents

- [Organization](#organization)
- [Built With](#built-with)
- [Getting Started](#getting-started)
- [Contributing](#contributing)

<!-- CONTRIBUTING -->

### Built With

- [yarn workspaces](https://classic.yarnpkg.com/en/docs/workspaces/)
- [react](https://reactjs.org/)
- [nextjs](https://nextjs.org/)
- [jest](https://github.com/facebook/jest)
- [ora](https://github.com/sindresorhus/ora)
- [commander](https://github.com/tj/commander.js/)
- [renovate](https://github.com/davidtheclark/cosmiconfig)

## Organization

This is organized as a Mono repo. It contains different packages that can be distributed separately:

### [core](https://github.com/webedx-spark/web-dependency-migration/tree/main/packages/core)

this package contains the stand alone functions that power up the cli and the eslint-plugin

### [cli](https://github.com/webedx-spark/web-dependency-migration/tree/main/packages/cli)

The command line will simplify listing and pulling local and 3rd party dependencies

### pull local and 3rd party dependencies

```bash
  dependency-migration pull <static/bundles/[bundleName]>
```

### Display dependencies that will be pulled into the bundle

```bash
  dependency-migration detect <static/bundles/[bundleName]>
```

### Pull all the local packages as dependencies

_We consider local packages to_

- Libraries: coursera written libraries located in `js/lib`
- Bundles: coursera bundleS imported within `static/bundles/`

```bash
    dependency-migration pull-local <static/bundles/[bundleName]>
```

### Pull only 3rd party dependencies:

```bash
  dependency-migration pull-3rd-party <static/bundles/[bundleName]>
```

### Add package.json to an existing dependency

If you are calling a dependency that does not have a package.json, you can fix this by running:

```bash
  dependency-migration fix-dependency-package <relative/path>
```

### [eslint-plugin](https://github.com/webedx-spark/web-dependency-migration/tree/main/packages/eslint-plugin)

The eslint-plugin will take care of replacing imports (when use with `--fix`) and prevent introducing local dependencies without package.json

## Contributing

Contributions are what makes the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request
