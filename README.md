# yarn-hello-world

[![Built with Looper][7]][6]

A "Hello world" project that uses [Yarn][1].

## Getting Started

### Download dependencies

```sh
yarn
```

### Run the app

```sh
yarn start
```

### Run the tests

```sh
yarn test
```

## CI

| Branch | Job | Status |
| --- | --- | --- |
| `master` | [`yarn-hello-world`][2] | [![Build Status][4]][2] |
| `test` | [`yarn-hello-world`][5] | [![Build Status][9]][5] |

### Looper

This repo was initially used to test Yarn support on Looper.

Support for Yarn on Looper has been added in Jan 2020, tracked in
[STRDTCI-29415][3].

This repo has been switched to use this new syntax in
9d5fb5d18023c9f2858d3be72fa33de4b27b0997.

A minimal `.looper.yml` file for a Node.js/Yarn project looks like this:

```yaml
tools:
  nodejs: 13.8.0
  yarn: 1.21.1
flows:
  default:
    - yarn
    - yarn test
```

Even though `yarn` is now a valid statement in the `tools` section, as of Feb
2020, access to Yarn's default package registry `yarnpkg.com` remains limited
and requires additional workarounds. Check the `test` branch for details.

```
There appears to be trouble with your network connection. Retrying...
```

## Links

The same exact project that uses npm instead of Yarn can be found here:

[`npm-hello-world`][8]

[1]: https://yarnpkg.com/lang/en/
[2]: https://ci.walmart.com/job/f0b00n7/job/yarn-hello-world/
[3]: https://jira.walmart.com/browse/STRDTCI-29415
[4]: https://ci.walmart.com/buildStatus/icon?job=f0b00n7/yarn-hello-world
[5]: https://ci.walmart.com/job/f0b00n7/job/yarn-hello-world-2
[6]: http://looper.walmart.com/
[7]: https://img.shields.io/badge/Built%20With-Looper-blue.svg
[8]: https://gecgithub01.walmart.com/f0b00n7/npm-hello-world
[9]: https://ci.walmart.com/buildStatus/icon?job=f0b00n7/yarn-hello-world-2
