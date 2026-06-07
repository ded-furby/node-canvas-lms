# node-canvas-lms


A very simple Node.js wrapper for the Canvas LMS API

## Usage
```js
var Canvas = require('node-canvas-lms');

var canvas = new Canvas('YOUR-HOST', {
  token: 'YOUR-TOKEN',
  version: 'v1',
});

canvas.get('courses', function (err, response, body) {
  if (err) {
    console.error(err);
    return;
  }

  console.log(body);
});
```

## API usage examples

```js
// Post with form data
canvas.post(
  'courses',
  { per_page: 100 },
  {
    name: 'Canvas API Example Course',
  },
  function (err, response, body) {
    if (err) {
      console.error(err);
      return;
    }

    console.log(response.statusCode, body.id);
  }
);
```

## Development

The master branch tracks the stable version, which is published to npm. Development occurs on the [dev branch][dev]. Currently This is going through a pretty big update, so be sure to check that out.

[dev]: https://github.com/cs10/node-canvas-lms/tree/dev
