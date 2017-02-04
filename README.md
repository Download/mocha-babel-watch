# mocha-babel-watch

[![Greenkeeper badge](https://badges.greenkeeper.io/Download/mocha-babel-watch.svg)](https://greenkeeper.io/)

**Demonstrates [issue #1987](https://github.com/mochajs/mocha/issues/1987) in Mocha JS**

## How to verify the issue

* Clone this repository
* Run `npm install` in the root of the cloned repo
* Run `npm run test-without-babel` to start mocha and have it keep watching
* Note the console output for the second test: `Try changing this message to verify that tests are re-run.`
* Locate file `test/without-babel.spec.js`, change the `console.log` message and save.
* Observe: The tests are re-run as expected
* Press `Ctrl+C` to interrupt mocha from watching
* Run `npm test-with-babel` to start mocha with `--require babel-register` and have it keep watching
* Observe: the second test, `re-runs the tests when some source file changes`, is failing
* Locate file `test/with-babel.spec.jsx`, remove the `throw` statement and save.
* Observe: The tests are not re-run.

