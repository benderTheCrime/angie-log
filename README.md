![emblem](https://rawgit.com/angie-framework/angie-log/master/svg/angie.svg "emblem")

## Angie Log
An extremely lightweight logging utility for NodeJS & the Angie Framework

[![npm version](https://badge.fury.io/js/angie-log.svg)](http://badge.fury.io/js/angie-log "npm version")
![iojs support](https://img.shields.io/badge/iojs-1.7.1+-brightgreen.svg "iojs support")
![node support](https://img.shields.io/badge/node-0.12.0+-brightgreen.svg "node support")
![npm downloads](https://img.shields.io/npm/dm/angie-log.svg "npm downloads")
![build status](https://travis-ci.org/benderTheCrime/angie-log.svg?branch=master "build status")
[![Coverage Status](https://coveralls.io/repos/benderTheCrime/angie-log/badge.svg?branch=master&service=github)](https://coveralls.io/github/benderTheCrime/angie-log?branch=master)
[![documentation](https://doc.esdoc.org/github.com/angie-framework/angie-log/badge.svg)](https://doc.esdoc.org/github.com/angie-framework/angie-log/ "documentation")

[![NPM](https://nodei.co/npm/angie-log.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/angie-log/)

### About
Angie Log is designed as an extremely lightweight logging utility for NodeJS which will:
* Prettify the terminal output using the [Chalk](https://www.npmjs.com/package/chalk "Chalk") package
* Provide utilities for printing useful and informative terminal output
* Create asynchronously written, non-blocking log files to maintain said useful and informative output based on well-defined JS log levels

### Usage
```bash
npm i -g angie-log
```
#### If Used Standalone
```javascript
import { default as Log } from 'angie-log';

// Call a new logger with defaults
let logger = new Log({
        outfile:    'log.log',              // Set the outfile
        file:       'log.log',              // Equivalent to `outfile`
        name:       'test',                 // Set the name of the logger
        timestamp:  true,                   // Controls whether the logfile output has a timestamp
        level:      'debug',                // Sets a single log level
        levels:     [ 'info', 'debug' ],    // Sets many available log levels
        logLevel:   'debug',                // Equivalent to `level`
        logLevels:  [ 'info', 'debug' ],    // Equivalent to `levels`
        silent:     false                   // Controls whether the log instance should output into the terminal as well
    }),
    err = new Log('log.log', 'test', true, 'error', false);

// Call the loggers with the string "test"
logger.info('test');
err.error('test');

// $setOutfile to change the output file
log.$setOutfile(`${process.cwd()}/angie.log`);

// $setName to change the name of the logger and what is logged in the outfile
log.$setOutfile('test');

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

#### If Used in an Angie Application
Include the module in the same fashion as it is above, or wherever called modules are bound:
```javascript
@Controller
class Test {
    constructor($Log) {
        $Log.info('The log module was included in a controller');
    }
}
```
The functions available on the Angie Log module are equivalent in either context.

For a list of Frequently Asked Questions, please see the [FAQ](https://github.com/benderTheCrime/angie-log/blob/master/md/FAQ.md "FAQ") and the [CHANGELOG](https://github.com/benderTheCrime/angie-log/blob/master/md/CHANGELOG.md "CHANGELOG") for an up to date list of changes. Contributors to this Project are outlined in the [CONTRIBUTORS](https://github.com/benderTheCrime/angie-log/blob/master/md/CONTRIBUTORS.md "CONTRIBUTORS") file.

### Angie
Please see the [site](http://benderthecrime.github.io/angie/) for information about the project, a quickstart guide, and documentation and the [CHANGELOG](https://github.com/benderTheCrime/angie/blob/master/md/CHANGELOG.md) for an up to date list of changes.