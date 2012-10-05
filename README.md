# SUIT button group

A SUIT component for creating a visual connection between UI buttons that
belong together.

Read more about [SUIT's design principles](https://github.com/necolas/suit/).

## Installation

* Download: [zip](https://github.com/necolas/suit-button-group/zipball/master)
* [Bower](https://github.com/twitter/bower/): `bower install suit-button-group`
* Git: `git clone https://github.com/necolas/suit-button-group.git`

## Available classes

* `btn-group` - The wrapper component around a group of `btn-group__item`
  components.
* `btn-group__item` - A `btn-group` sub-object used to contain other nodes.

## Usage

An element with the `btn-group` class must be used to wrap a collection of
elements with the `btn-group__item` class. The `btn-group` component *must*
only contain `btn-group__item` components as children.

The button group items may contain other components, e.g., [SUIT
button](https://github.com/necolas/suit-button) or buttons with dropdown
menus.

```html
<div class="btn-group">
    <div class="btn-group__item">
        <a class="btn" href="#">Dashboard</a>
    </div>
    <div class="btn-group__item">
        <a class="btn" href="#">Settings</a>
    </div>
    <div class="btn-group__item with-dropdown">
        <a class="btn js-dropdown-toggle" href="#">
            Account
            <i class="icon icon--caret"></i>
        </a>
        <div class="dropdown-menu">
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
.btn-group__item {
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

.btn + .btn,
.btn + .btn-group,
.btn-group + .btn,
.btn-group + .btn-group {
    margin-left: 5px;
}
```

## Browser support

* Google Chrome (latest)
* Opera (latest)
* Firefox 4+
* Safari 5+
* Internet Explorer 8+
