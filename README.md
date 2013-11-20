# SUIT button group

A SUIT component for creating a visual connection between UI buttons that
belong together.

Read more about [SUIT's design principles](https://github.com/suitcss/suit/).

## Installation

* [Bower](http://bower.io/): `bower install --save suit-button-group`
* [Component(1)](http://component.io/): `component install suitcss/button-group`
* Download: [zip](https://github.com/suitcss/button-group/zipball/master)
* Git: `git clone https://github.com/suitcss/button-group.git`

## Available classes

* `ButtonGroup` - The core component.
* `ButtonGroup--hz` - Horizontally arranged buttons.
* `ButtonGroup-item` - A `ButtonGroup` sub-object used to contain buttons.

### Plugins

The `button-group.plugins.css` file provides the following classes:

* `ButtonGroup--borderCollapse` - Collapse the borders between buttons.

## Use

An element with the `ButtonGroup` class must be used to wrap a collection of
elements with the `ButtonGroup-item` class. The `ButtonGroup` component *must*
only contain `ButtonGroup-item` components as children.

The button group items may contain other components, e.g., [SUIT
button](https://github.com/suitcss/button) or buttons with dropdown
menus.

```html
<div class="ButtonGroup">
    <div class="ButtonGroup-item">
        <a class="Button" href="#">Dashboard</a>
    </div>
    <div class="ButtonGroup-item">
        <a class="Button" href="#">Settings</a>
    </div>
    <div class="ButtonGroup-item js-dropdownContainer">
        <a class="Button js-dropdownToggle" href="#">
            Account
            <span class="Icon Icon--caret"></span>
        </a>
        <div class="Dropdown">
            ...
        </div>
    </div>
</div>
```

or

```html
<ul class="ButtonGroup">
    <li class="ButtonGroup-item">
        <a class="Button" href="#">Dashboard</a>
    </li>
    <li class="ButtonGroup-item">
        <a class="Button" href="#">Settings</a>
    </li>
    <li class="ButtonGroup-item js-dropdownContainer">
        <a class="Button js-dropdownToggle" href="#">
            Account
            <span class="Icon Icon--caret"></span>
        </a>
        <div class="Dropdown">
            ...
        </div>
    </li>
</ul>
```


## Customising

Your application-level CSS can build upon this component.

```css
/**
 * Override default the `ButtonGroup-item` vertical alignment.
 */

.ButtonGroup--alignMiddle > .ButtonGroup-item {
    vertical-align: middle;
}
```

If your app's button theme uses a border width other than `1px`, you can adjust the
button group component to accommodate this. For example, if your buttons used
3px borders, you would add this code to your application's `button-group.css` file:

```css
/**
 * Override default `ButtonGroup--borderCollapse`
 */

.ButtonGroup--borderCollapse.ButtonGroup--hz .ButtonGroup-item {
    margin-left: -3px;
}

.ButtonGroup--borderCollapse:not(.ButtonGroup--hz) .ButtonGroup-item {
    margin-top: -3px;
}
```

Or if you have buttons with different width borders, you could create new modifiers.

```css
/**
 * Use with `ButtonGroup--borderCollapse`
 */

.ButtonGroup--borderCollapse10px.ButtonGroup--hz .ButtonGroup-item {
    margin-left: -10px;
}

.ButtonGroup--borderCollapse10px:not(.ButtonGroup--hz) .ButtonGroup-item {
    margin-top: -10px;
}
```

## Testing

Install [Node](http://nodejs.org) (comes with npm). It's recommended that you
also globally install [Component(1)](http://component.io): `npm install -g
component`.

From the repo root, install the project's development dependencies:

```
make
```

To run the CSS Lint tests and build the front-end development bundle:

```
make test
```

Basic visual tests are in `test.html`.

## Browser support

* Google Chrome (latest)
* Opera (latest)
* Firefox 4+
* Safari 5+
* Internet Explorer 9+
