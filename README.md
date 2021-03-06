# Winston TCP [![version][npm-version]][npm-url] [![License][license-image]][license-url]

> TCP transport for [Winston](https://github.com/winstonjs/winston)

[![Build Status][travis-image]][travis-url]
[![Downloads][npm-downloads]][npm-url]
[![Code Climate][codeclimate-quality]][codeclimate-url]
[![Coverage Status][codeclimate-coverage]][codeclimate-url]
[![Dependency Status][dependencyci-image]][dependencyci-url]
[![Dependencies][david-image]][david-url]

## Install

```bash
npm install --only=production --save winston-tcp
```

## API

```js
import Transport from 'winston-tcp'

let logger = new (winston.Logger)({
  transports: [
    new (Transport)({
      host: '127.0.0.1',
      port: 1337,
      json: true,
      timestamp: true
    })
  ]
})

logger.log('info', 'foo')
```

or simply:

```js
import winston from 'winston'
import Transport from 'winston-tcp'

winston.add(new Transport({
  host: '127.0.0.1',
  port: 1337
}))

winston.info('foo')
```

## Options

Name                | Description                                                                   | Default
------------------- | ----------------------------------------------------------------------------- | -------
`host`              | The host to connect to                                                        | none
`port`              | The server port to connect to                                                 | none
`reconnectInterval` | Time to pause between disconnect and reconnect (in ms)                        | `1000`
`bufferLength`      | Number of messages to buffer while disconnected, set to `false` for unlimited | `10000`
`json`              | If `true`, messages will be logged as JSON                                    | `false`
`timestamp`         | flag indicating if we should prepend output with timestamps                   | `false`
`formatter`         | a custom formatter (see Winston docs)                                         | none

---
> :copyright: [ahmadnassri.com](https://www.ahmadnassri.com/)  · 
> License: [ISC][license-url]  · 
> Github: [@ahmadnassri](https://github.com/ahmadnassri)  · 
> Twitter: [@ahmadnassri](https://twitter.com/ahmadnassri)

[license-url]: http://choosealicense.com/licenses/isc/
[license-image]: https://img.shields.io/github/license/ahmadnassri/winston-tcp.svg?style=flat-square

[travis-url]: https://travis-ci.org/ahmadnassri/winston-tcp
[travis-image]: https://img.shields.io/travis/ahmadnassri/winston-tcp.svg?style=flat-square

[npm-url]: https://www.npmjs.com/package/winston-tcp
[npm-version]: https://img.shields.io/npm/v/winston-tcp.svg?style=flat-square
[npm-downloads]: https://img.shields.io/npm/dm/winston-tcp.svg?style=flat-square

[codeclimate-url]: https://codeclimate.com/github/ahmadnassri/winston-tcp
[codeclimate-quality]: https://img.shields.io/codeclimate/github/ahmadnassri/winston-tcp.svg?style=flat-square
[codeclimate-coverage]: https://img.shields.io/codeclimate/coverage/github/ahmadnassri/winston-tcp.svg?style=flat-square

[david-url]: https://david-dm.org/ahmadnassri/winston-tcp
[david-image]: https://img.shields.io/david/ahmadnassri/winston-tcp.svg?style=flat-square

[dependencyci-url]: https://dependencyci.com/github/ahmadnassri/winston-tcp
[dependencyci-image]: https://dependencyci.com/github/ahmadnassri/winston-tcp/badge?style=flat-square
