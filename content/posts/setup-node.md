---
title: setup-node
date: 2024-04-06T12:19:06+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1711344209056-37639a63f70a?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MTIzNzY5Njl8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1711344209056-37639a63f70a?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MTIzNzY5Njl8&ixlib=rb-4.0.3
---

# [actions/setup-node](https://github.com/actions/setup-node)

# setup-node

<p align="left">
  <a href="https://github.com/actions/setup-node/actions?query=workflow%3Abuild-test"><img alt="build-test status" src="https://github.com/actions/setup-node/workflows/build-test/badge.svg"></a> <a href="https://github.com/actions/setup-node/actions?query=workflow%3Aversions"><img alt="versions status" src="https://github.com/actions/setup-node/workflows/versions/badge.svg"></a> <a href="https://github.com/actions/setup-node/actions?query=workflow%3Aproxy"><img alt="proxy status" src="https://github.com/actions/setup-node/workflows/proxy/badge.svg"></a> 
</p>

This action sets by node environment for use in actions by:

- optionally downloading and caching a version of node - npm by version spec and add to PATH
- registering problem matchers for error output
- configuring authentication for GPR or npm

# v2-beta

A beta release which adds reliability for pulling node distributions from a cache of node releases is available by referencing the `v2-beta` tag.

```yaml
steps:
- uses: actions/checkout@v2
- uses: actions/setup-node@v2-beta
  with:
    node-version: '12'
```

The action will first check the local cache for a semver match. The hosted images have been updated with the latest of each LTS from v8, v10, v12, and v14. `self-hosted` machines will benefit from the cache as well only downloading once. The action will pull LTS versions from [node-versions releases](https://github.com/actions/node-versions/releases) and on miss or failure will fall back to the previous behavior of downloading directly from [node dist](https://nodejs.org/dist/).

The `node-version` input is optional. If not supplied, the node version that is PATH will be used. However, this action will still register problem matchers and support auth features. So setting up the node environment is still a valid scenario without downloading and caching versions.

# Usage

See [action.yml](action.yml)

Basic:
```yaml
steps:
- uses: actions/checkout@v2
- uses: actions/setup-node@v1
  with:
    node-version: '12'
- run: npm install
- run: npm test
```

Check latest version:

In the basic example above, the `check-latest` flag defaults to `false`. When set to `false`, the action tries to first resolve a version of node from the local cache. For information regarding locally cached versions of Node on GitHub hosted runners, check out [GitHub Actions Virtual Environments](https://github.com/actions/virtual-environments). The local version of Node in cache gets updated every couple of weeks. If unable to find a specific version in the cache, the action will then attempt to download a version of Node. Use the default or set `check-latest` to `false` if you prefer stability and if you want to ensure a specific version of Node is always used.

If `check-latest` is set to `true`, the action first checks if the cached version is the latest one. If the locally cached version is not the most up-to-date, a version of Node will then be downloaded. Set `check-latest` to `true` it you want the most up-to-date version of Node to always be used.

> Setting `check-latest` to `true` has performance implications as downloading versions of Node is slower than using cached versions

```yaml
steps:
- uses: actions/checkout@v2
- uses: actions/setup-node@v2
  with:
    node-version: '12'
    check-latest: true
- run: npm install
- run: npm test
```

Matrix Testing:
```yaml
jobs:
  build:
    runs-on: ubuntu-16.04
    strategy:
      matrix:
        node: [ '10', '12' ]
    name: Node ${{ matrix.node }} sample
    steps:
      - uses: actions/checkout@v2
      - name: Setup node
        uses: actions/setup-node@v1
        with:
          node-version: ${{ matrix.node }}
      - run: npm install
      - run: npm test
```

Publish to npmjs and GPR with npm:
```yaml
steps:
- uses: actions/checkout@v2
- uses: actions/setup-node@v1
  with:
    node-version: '10.x'
    registry-url: 'https://registry.npmjs.org'
- run: npm install
- run: npm publish
  env:
    NODE_AUTH_TOKEN: ${{ secrets.NPM_TOKEN }}
- uses: actions/setup-node@v1
  with:
    registry-url: 'https://npm.pkg.github.com'
- run: npm publish
  env:
    NODE_AUTH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Publish to npmjs and GPR with yarn:
```yaml
steps:
- uses: actions/checkout@v2
- uses: actions/setup-node@v1
  with:
    node-version: '10.x'
    registry-url: <registry url>
- run: yarn install
- run: yarn publish
  env:
    NODE_AUTH_TOKEN: ${{ secrets.YARN_TOKEN }}
- uses: actions/setup-node@v1
  with:
    registry-url: 'https://npm.pkg.github.com'
- run: yarn publish
  env:
    NODE_AUTH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Use private packages:
```yaml
steps:
- uses: actions/checkout@v2
- uses: actions/setup-node@v1
  with:
    node-version: '10.x'
    registry-url: 'https://registry.npmjs.org'
# Skip post-install scripts here, as a malicious
# script could steal NODE_AUTH_TOKEN.
- run: npm install --ignore-scripts
  env:
    NODE_AUTH_TOKEN: ${{ secrets.NPM_TOKEN }}
# `npm rebuild` will run all those post-install scripts for us.
- run: npm rebuild && npm run prepare --if-present
```


# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)

# Contributions

Contributions are welcome!  See [Contributor's Guide](docs/contributors.md)

## Code of Conduct

:wave: Be nice.  See [our code of conduct](CONDUCT)
