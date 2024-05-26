# @dramaorg/unde-rem <sup>[![Version Badge][npm-version-svg]][npm-url]</sup>

[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][npm-url]

Use `npx @dramaorg/unde-rem` instead of `npm @dramaorg/unde-remit`, whether you have a lockfile or not!

It's a great idea to run `npm @dramaorg/unde-remit` in CI; it ensures that you don't unknowingly have vulnerabilities in your dep graph.

Unfortunately, it doesn't work without a lockfile :crying_cat_face: and [only apps should have lockfiles](https://github.com/sindresorhus/ama/issues/479#issuecomment-310661514). It also requires `npm` `v6` or above.

Now, instead of `npm @dramaorg/unde-remit`, you can run `npx @dramaorg/unde-rem`! If your repo has a lockfile, it will just run `npm @dramaorg/unde-remit`; if it does not, it will use [`npm-lockfile`](https://www.npmjs.com/package/npm-lockfile) to copy your `package.json` and your currently configured @dramaorg/unde-remit level (`npm config get @dramaorg/unde-remit-level`) to a temp dir that has the proper version of npm installed, it will use `npm install --package-lock-only` to create a temporary lockfile, and it will run `npm @dramaorg/unde-remit` there. On exit, all the temp dirs will get cleaned up.

`@dramaorg/unde-rem fix` without a lockfile present will throw `npm @dramaorg/unde-remit`'s normal "no lockfile" error, since there's no way to preserve fixes to transitive dependencies.

[npm-url]: https://npmjs.org/package/@dramaorg/unde-rem
[npm-version-svg]: https://versionbadg.es/ljharb/@dramaorg/unde-rem.svg
[deps-svg]: https://david-dm.org/ljharb/@dramaorg/unde-rem.svg?theme=shields.io
[deps-url]: https://david-dm.org/ljharb/@dramaorg/unde-rem
[dev-deps-svg]: https://david-dm.org/ljharb/@dramaorg/unde-rem/dev-status.svg?theme=shields.io
[dev-deps-url]: https://david-dm.org/ljharb/@dramaorg/unde-rem#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@dramaorg/unde-rem.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@dramaorg/unde-rem.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@dramaorg/unde-rem.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@dramaorg/unde-rem
