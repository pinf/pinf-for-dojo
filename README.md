*Status: DEV*
[![Circle CI](https://circleci.com/gh/pinf/pinf-for-dojo.svg?style=svg)](https://circleci.com/gh/pinf/pinf-for-dojo)

PINF JavaScript Loader for Dojo 2
=================================

A [Dojo 2 Loader](https://github.com/dojo/loader) [plugin](http://requirejs.org/docs/plugins.html) for
loading [PINF JavaScript Bundles](https://github.com/pinf/pinf-loader-js).

Any portable bundle may be loaded. Modules and packages written for Dojo may also
be [bundled](https://github.com/pinf-it/pinf-it-bundler) and loaded via the
[PINF JavaScript Bundle Loader](https://github.com/pinf/pinf-loader-js) potentially eliminating
the need for the Dojo loader.


Install
-------

    npm install pinf-for-dojo


Usage
-----

`http://localhost/index.html`

    <script src="dojo/loader.js"></script>
    <script>
        require({
            paths: {
                pinf: "pinf.require"
            }
        }, [
            "pinf!bundle"
        ], function(sandbox) {
            sandbox.main();
        });
    </script>

`http://localhost/bundle.js`

    PINF.bundle("", function(require) {
        require.memoize("/main.js", function(require, exports, module) {
            exports.main = function(options) {
                console.log("HelloWorld!");
            }
        });
    });


Test & Development
==================

Requirements:

  * [NodeJS](http://nodejs.org/)

Run tests:

    npm test

Launch development workspace:

    npm run dev
    open http://localhost:8080/

Build
-----

    npm run build


License
=======

[UNLICENSE](http://unlicense.org/)
