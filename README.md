# yarn-hello-world

A simple "Hello world" project that uses [Yarn][1].

## Run the project

```sh
yarn
yarn start
```

## CI

| Branch | Job | Status |
| --- | --- | --- |
| `master` | [`yarn-hello-world-master`][2] | [![Build Status][6]][7] |
| `looper-yarn` | [`yarn-hello-world-looper-yarn`][5] | [![Build Status][8]][9] |

### Looper

Currently (as of Oct 2019), Looper does not natively support Yarn, requiring
_manual_ download and installation of Yarn prior to being able to use it. This
in turn leads to having to globally modify slave state, and slower builds.

A ticket has been opened to track progress on adding full support for Yarn on
Looper: [STRDTCI-29415][3]

The goal is to have a simple, minimal `.looper.yml` file with the following
structure:

```yaml
tools:
  nodejs: 13.2.0
  yarn: 1.19.2
flows:
  default:
    - yarn
    - yarn start
```

This `.looper.yml` file can be found on the `looper-yarn` branch, and the diff
can be seen here:

[master..looper-yarn][4]

Once support is available, both build jobs seen above should be green.

[1]: https://yarnpkg.com/lang/en/
[2]: https://ci.walmart.com/job/f0b00n7/job/yarn-hello-world-master/
[3]: https://jira.walmart.com/browse/STRDTCI-29415
[4]: https://gecgithub01.walmart.com/f0b00n7/yarn-hello-world/compare/master..looper-yarn
[5]: https://ci.walmart.com/job/f0b00n7/job/yarn-hello-world-looper-yarn/
[6]: https://ci.walmart.com/buildStatus/icon?job=f0b00n7/yarn-hello-world-master
[7]: https://ci.walmart.com/job/f0b00n7/job/yarn-hello-world-master/
[8]: https://ci.walmart.com/buildStatus/icon?job=f0b00n7/yarn-hello-world-looper-yarn
[9]: https://ci.walmart.com/job/f0b00n7/job/yarn-hello-world-looper-yarn/
