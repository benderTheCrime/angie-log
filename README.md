## Angie Log

This is a very slim terminal and outfile logger for iojs/NodeJS ES6 projects. It will work standalone, or as an extension to the [Angie MVC](https://github.com/benderTheCrime/angie).

![build status](https://travis-ci.org/benderTheCrime/angie-log.svg?branch=master "build status")
![iojs support](https://img.shields.io/badge/iojs-1.7.1+-brightgreen.svg "iojs support")
![node support](https://img.shields.io/badge/node-0.12.0+-brightgreen.svg "node support")
![code coverage](https://rawgit.com/benderTheCrime/angie-log/master/svg/coverage.svg "code coverage")
![npm downloads](https://img.shields.io/npm/dm/angie-log.svg "npm downloads")

[![NPM](https://nodei.co/npm/angie-log.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/angie-log/)


### Usage
```bash
npm i -g angie-log
```

```javascript
import {default as Log} from 'angie-log';

// Call a new logger with defaults
let logger = new Log({
        outfile:    'log.log',
        file:       'log.log',
        name:       'test',
        timestamp:  true,
        level:      'debug',
        silent:     false
    }),
    err = new Log('log.log', 'test', true, 'error', false);

// Output to log.log
logger.info('test');
err.error('test');

// $setOutfile to change the output file
log.$setOutfile(`${process.cwd()}/angie.log`);

// $setTimestamp to toggle timestamps in the log output
log.$setTimestamp(true);

// $setLevel to change the log level
log.$setLevel(true);

// $setSilent to prevent terminal output
log.$setSilent(true);

// Explicitly call the prettified terminal output
Log.info('test');
Log.debug('test');
Log.warn('test');
Log.error('test');
```

### About
Angie Log is designed as an extremely lightweight logging utility for NodeJS which will:
    * Prettify the terminal output using the [Chalk](https://www.npmjs.com/package/chalk "Chalk") package
    * Provide utilities for printing useful and informative terminal output
    * Create asynchronous, non-blocking log files to maintain said useful and informative terminal output based on well-defined JS log levels


- method arguments and their meanings
- note about calling a level outside of it's type

### Angie
Please see the [site](http://benderthecrime.github.io/angie/#/about) for news, a quickstart guide, and documentation and the [CHANGELOG](https://github.com/benderTheCrime/angie-log/blob/master/CHANGELOG.md) for an up to date list of changes.
