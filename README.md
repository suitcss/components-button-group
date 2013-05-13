# SUIT button group

A SUIT component for creating a visual connection between UI buttons that
belong together.

Read more about [SUIT's design principles](https://github.com/necolas/suit/).

## Installation

* [Bower](http://bower.io/): `bower install --save suit-button-group`
* Download: [zip](https://github.com/necolas/suit-button-group/zipball/master)
* Git: `git clone https://github.com/necolas/suit-button-group.git`

## Available classes

* `ButtonGroup` - The wrapper component around a group of `ButtonGroup-item`
  components.
* `ButtonGroup-item` - A `ButtonGroup` sub-object used to contain other nodes.

## Usage

An element with the `ButtonGroup` class must be used to wrap a collection of
elements with the `ButtonGroup-item` class. The `ButtonGroup` component *must*
only contain `ButtonGroup-item` components as children.

The button group items may contain other components, e.g., [SUIT
button](https://github.com/necolas/suit-button) or buttons with dropdown
menus.

```html
<div class="ButtonGroup">
    <div class="ButtonGroup-item">
        <a class="Button" href="#">Dashboard</a>
    </div>
    <div class="ButtonGroup-item">
        <a class="Button" href="#">Settings</a>
    </div>
    <div class="ButtonGroup-item with-Dropdown">
        <a class="Button js-dropdownToggle" href="#">
            Account
            <i class="Icon Icon--caret"></i>
        </a>
        <div class="Dropdown">
            ...
        </div>
    </div>
</div>
```

This component should intelligently remove certain `border-radius` values from
your application-level button theme.

## Customising

Your application-level CSS can build upon this component.

If your app's button theme uses a border width other than `1px`, you can adjust the
button group component to accommodate this. For example, if your buttons used
3px borders, you would add this rule to your application-level CSS:

```css
.ButtonGroup-item {
    margin-left: -3px;
}
```

If you need to adjust the space between buttons, or buttons and button groups,
or multiple button groups, you might want to add a rule like this to your
application-level CSS:

```css
/**
 * Add some space between adjacent .btn and .btn-group components
 */

.Button + .Button,
.Button + .ButtonGroup,
.ButtonGroup + .Button,
.ButtonGroup + .ButtonGroup {
    margin-left: 5px;
}
```

## Browser support

* Google Chrome (latest)
* Opera (latest)
* Firefox 4+
* Safari 5+
* Internet Explorer 8+
