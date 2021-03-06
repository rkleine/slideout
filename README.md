# slideout [![Build Status](https://secure.travis-ci.org/Mango/slideout.png)](http://travis-ci.org/Mango/slideout) [![devDependency Status](https://david-dm.org/Mango/slideout/dev-status.png)](https://david-dm.org/Mango/slideout#info=devDependencies)

> A touch slideout navigation menu for your mobile web apps.

## Demo

[Check out the demo](https://mango.github.io/slideout/) to see it in action (on your mobile or emulate touches on your browser).

<img src="http://i.imgur.com/AWgwlVW.gif" alt="Slideout.js demo">

## Installation

    $ npm install slideout

    $ bower install slideout

    $ component install mango/slideout

## Usage

### HTML
```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="cleartype" content="on">
    <meta name="MobileOptimized" content="320">
    <meta name="HandheldFriendly" content="True">
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>Slideout Demo</title>
  </head>
  <body>

    <nav id="menu">
      <header>
        <h2>Menu</h2>
      </header>
    </nav>

    <main id="main">
      <header>
        <button class="btn js-slideout-toggle">☰</button>
        <h2>Panel</h2>
      </header>
    </main>

    <script src="slideout.js"></script>
  </body>
</html>
```

### CSS
You should add the following CSS in your application.

```css
html,
body {
  width: 100%;
  height: 100%;
}

.slideout-menu {
  position: fixed;
  left: 0;
  top: 0;
  bottom: 0;
  right: 0;
  z-index: 0;
  width: 256px;
  overflow-y: scroll;
  -webkit-overflow-scrolling: touch;
  display: none;
}

.slideout-panel {
  position: relative;
  z-index: 1;
  transform: translate3d(0, 0, 0);
}

.slideout-open,
.slideout-open body {
  overflow: hidden;
}

.slideout-open .slideout-menu {
  display: block;
}
```

### JavaScript
```js
var slideout = new Slideout({
  'panel': document.getElementById('main'),
  'menu': document.getElementById('menu'),
  'padding': 256,
  'tolerance': 70
});
```

## API

### Slideout(options)
Create a new instance of `Slideout`.

- `options` (Object) - Options to customize a new instance of Slideout.
- `options.panel` (HTMLElement) - The DOM element that contains all your application content (`.slideout-panel`).
- `options.menu` (HTMLElement) - The DOM element that contains your menu application (`.slideout-menu`).
- `[options.duration]` (Number) - The time (milliseconds) to open/close the slideout. Default: `300`.
- `[options.fx]` (String) - The CSS effect to use when animating the opening and closing of the slideout. Default: `ease`.
- `[options.padding]` (Number) - Default: `256`.
- `[options.tolerance]` (Number) - Default: `70`.

```js
var slideout = new Slideout({
  'panel': document.getElementById('main'),
  'menu': document.getElementById('menu'),
  'padding': 256,
  'tolerance': 70
});
```

### Slideout.open();
Opens the slideout menu.

```js
slideout.open();
```

### Slideout.close();
Closes the slideout menu.

```js
slideout.close();
```

### Slideout.toggle();
Toggles (open/close) the slideout menu.

```js
slideout.toggle();
```

### Slideout.isOpen();
Returns `true` if the slideout is currently open, and `false` if it is closed.

```js
slideout.isOpen(); // true or false
```

## npm-scripts
```
$ npm run build
```

```
$ npm run dist
```

```
$ npm test
```

## With ❤ by
- Guille Paz (Front-end developer | Web standards lover)
- E-mail: [guille87paz@gmail.com](mailto:guille87paz@gmail.com)
- Twitter: [@pazguille](http://twitter.com/pazguille)
- Web: [http://pazguille.me](http://pazguille.me)

## License
MIT license. Copyright © 2015 [Mango](http://getmango.com).
