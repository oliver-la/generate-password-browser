# generate-password-browser (w/ Angular Support) [![Build Status](https://api.travis-ci.org/xama5/generate-password-browser.svg?branch=master)](https://travis-ci.org/xama5/generate-password-browser)

[![Generate-Password NPM](https://nodei.co/npm/generate-password-browser.png?downloads=true&downloadRank=true)](http://npmjs.org/package/generate-password-browser)


Generate Password is a (relatively) extensive library for generating random and unique passwords in browsers.
This is a fork of the original generate-password package https://github.com/brendanashworth/generate-password, but unfortunately it doesn't and [won't](https://github.com/brendanashworth/generate-password/pull/21) support browsers.
Confirmed to be working with Angular 4, 5 and 6 in these browsers:

- Google Chrome 60.0.3112.113
- Firefox 55.0.3
- Internet Explorer 11

## Install

```bash
$ npm install generate-password-browser --save
```

## Usage

#### `generate([options])`

Generate one password with the given options. Returns a string.

```javascript
var generator = require('generate-password-browser');

var password = generator.generate({
	length: 10,
	numbers: true
});

// 'uEyMTw32v9'
console.log(password);
```

#### `generateMultiple(amount[, options])`

Bulk generate multiple passwords at once, with the same options for all. Returns an array.

```javascript
var generator = require('generate-password-browser');

var passwords = generator.generateMultiple(3, {
	length: 10,
	uppercase: false
});

// [ 'hnwulsekqn', 'qlioullgew', 'kosxwabgjv' ]
console.log(passwords);
```

### Available options
Any of these can be passed into the options object for each function.

| Name                     | Description                                                           | Default Value |
|--------------------------|-----------------------------------------------------------------------|---------------|
| length                   | Integer, length of password.                                          | 10            |
| numbers*                 | Boolean, put numbers in password.                                     | false         |
| symbols*                 | Boolean or String, put symbols in password.                           | false         |
| lowercase*               | Boolean, put lowercase in password                                    | true          |
| uppercase*               | Boolean, use uppercase letters in password.                           | true          |
| excludeSimilarCharacters | Boolean, exclude similar chars, like 'i' and 'l'.                     | false         |
| exclude                  | String, characters to be excluded from password.                      | ''            |
| strict                   | Boolean, password must include at least one character from each pool. | false         |

*At least one should be true.
