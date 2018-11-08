# gulp-json-modify-plus

[![Build Status](https://travis-ci.org/OLIOEX/gulp-json-modify.png?branch=master)](https://travis-ci.org/OLIOEX/gulp-json-modify-plus)

[![NPM version](https://badge.fury.io/js/gulp-json-modify.png)](http://badge.fury.io/js/gulp-json-modify-plus)

> Replace data in a JSON file with something else

## Usage

#### Install

```bash
$ npm install gulp-json-modify-plus --save
```

## Example

```js
// jsonModify data in multiple files
gulp.task('jsonModify', function () {

  return gulp.src([ './bower.json', './package.json' ])
    .pipe(tasks.jsonModify({
      key: 'version',
      value: '1.0.0'
    }))
    .pipe(gulp.dest('./'))

})

// Run the gulp tasks
gulp.task('default', function(){
  gulp.run('jsonModify')
})
```

## Options

* **key**: key to replace (required)
* **value**: set to value (if value === undefined The plugin will delete `obj.key`)

Example:

```js
.pipe(jsonModify({ key: 'app_id', value: '1234' })
```

##### Dot notation is supported for sub-keys

```js

.pipe(jsonModify({ key: 'key.subkey', value: 'set-me-to' }))

/*
{
  "key": {
    "subkey": "<value>"
  }
}
*/
```

### options.indent

Set the amount of spaces for indentation in the result JSON file.

## /ht

https://github.com/stevelacy/gulp-bump

## LICENSE

(MIT License)

Copyright (c) 2015 Steve Lacy <me@slacy.me> slacy.me

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
