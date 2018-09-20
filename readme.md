# idle-until-urgent

Inspired directly by [this 💯 post by Philip Walton](https://philipwalton.com/articles/idle-until-urgent/), but uses a function-based API instead of classes.

Fetch resources lazily - either whenever the browser is next idle, or when you request the resource.

In a browser that doesn't have [requestIdleTimeout](https://caniuse.com/#feat=requestidlecallback), or in node.js, falls back to `setTimeout(fn, 1000)`.

## Install

```sh
npm i idle-until-urgent
```

```
const makeIdleGetter = require('idle-until-urgent')
```

## Usage

<!--js
const makeIdleGetter = require('./')
-->

```js
const getFormatter = makeIdleGetter(() => new Intl.DateTimeFormat('en-US', {
	timeZone: 'America/Los_Angeles',
}))

// later in your code, presumably not during the first tick...

getFormatter().format(new Date(1537452915210)) // => '9/20/2018'

```

## License

[WTFPL](http://wtfpl2.com)
