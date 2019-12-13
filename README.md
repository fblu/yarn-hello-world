# yarn-hello-world

A "Hello world" project that uses [Yarn][1].

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

Currently (as of Oct 2019), Walmart's build infrastructure [Looper][10] does not
natively support Yarn. Projects using Yarn require _manual_ download,
installation, and initialization of additional software prior to being able to
use their package manager. This in turn leads to globally modified machine
state, slower builds, and other potential issues.

Yarn is the default package manager for many projects, including almost all
repositories related to React Native. Mixing package managers (i.e. using _both_
NPM and Yarn in the same project) leads to inconsistencies with lock files and
may result in broken builds (depending on how the lock files are managed).

A ticket has been opened to track progress on adding full support for Yarn on
Looper: [STRDTCI-29415][3]

A minimal `.looper.yml` file for a Node.js/Yarn project would have the following
structure:

```yaml
tools:
  nodejs: 13.3.0
  yarn: 1.21.1
flows:
  default:
    - yarn
    - yarn test
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
[10]: http://looper.walmart.com/
