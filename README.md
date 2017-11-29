# Direction Reveal

[Live demo](http://nigelotoole.github.io/direction-reveal/)

## Direction aware content reveals
This plugin detects which direction a user enters/exits a block, allowing you to reveal/hide content based on this direction.
The hidden content can animate in from the direction the user enters and animate out the direction the user leaves, allowing you to create interesting animation effects.



## Installation
```javascript
$ npm install direction-reveal --save-dev
```


## Usage

### Import

The script is an ES6(ES2015) module but a compiled version is included in the build as index.js. You can also copy scripts/direction-reveal.js into your own site if your build process can accomodate ES6 modules, Babel and Browserify are used in the demo site.

```javascript
import DirectionReveal from 'direction-reveal';

// Init with default setup
const directionRevealDemo = DirectionReveal();

// Init with all options at default setting
const directionRevealSwing = DirectionReveal({
  selector: '.direction-reveal',              // Container element selector.
  itemSelector: '.direction-reveal__card',    // Item element selector.
  animationName: 'swing',                     // Animation CSS class.
  enableTouch: true,                          // Adds touch event to show content on first click then follow link on the second click.
  touchThreshold: 250                         // Touch length must be less than this to trigger reveal which prevents the event triggering if user is scrolling.
});
```


### HTML

```html
  &lt;div class="direction-reveal"&gt;

    &lt;a href="#" class="direction-reveal__card"&gt;
      &lt;img src="images/image.jpg" alt="Image" class="img-fluid"&gt;

      &lt;div class="direction-reveal__overlay"&gt;
        &lt;h3 class="direction-reveal__title"&gt;Title&lt;/h3&gt;
        &lt;p class="direction-reveal__text"&gt;Description text.&lt;/p&gt;
      &lt;/div&gt;
    &lt;/a&gt;

    ...

  &lt;/div&gt;
```


### Using other tags
The demos use &lt;a&gt; tags for the "direction-reveal__card" but a &lt;div&gt; can be used as below, specifiying the tabindex ensures keyboard navigation works as expected. They can all have a value of 0 and will follow the source order of the divs.

```html
&lt;div class="direction-reveal__card" tabindex="0"&gt;
  ...
&lt;/div&gt;
```

### Touch support
The plugin will detect touch support and reveal the hidden content on first click then follow link on the second click. This can be disabled in the options.



## Demo site
Clone or download from Github.

```javascript
$ npm install
$ gulp serve
```


### License
MIT © Nigel O Toole
