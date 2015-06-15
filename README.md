# plastik-selector

`plastik-selector` extends `iron-selector` to provide several extra features in addition to basic
selection, namely required selections and reset items. `plastik-selector` is very similar to
`iron-selector` and meant to be able to function as a drop-in replacement, and therefore it uses
the same events and classes as `iron-selector` does.

Demos and documentation are available on the [component page](http://www.plastikit.org/1.x/#!/components/plastik-selector).

Pull requests are always welcome. If you encounter any bugs, please feel free to [submit an issue](https://github.com/Plastikit/plastik-selector/issues/new/).

## Installation

```sh
bower install Plastikit/plastik-option-list --save
```

## Basic usage

 > _See more at the [component page](http://www.plastikit.org/1.x/#!/components/plastik-selector)_ 

Clicking or tapping on an item selects it. `selected` indicates which item is being selected.
By default, the index of the item is used.

### Example
```html
    <plastik-selector selected="0">
      <div>Item 1</div>
      <div>Item 2</div>
      <div>Item 3</div>
    </plastik-selector>
 ```
## Selecting by attribute values

If you want to use the attribute value of an element for `selected` instead of the index,
set `attrForSelected` to the name of the attribute. For example, if you want to select items by
`name`, set `attrForSelected` to `name`.

### Example
```html
    <plastik-selector attr-for-selected="name" selected="foo">
      <div name="foo">Foo</div>
      <div name="bar">Bar</div>
      <div name="zot">Zot</div>
    </plastik-selector>
 ```
## Requiring selection
 
 If you would like to enforce that at least one item is selected at all times, set `required` to
 true. If no default selection is specified, `selected` will default to the first item in the list.
 
### Example
 ```html
     <plastik-selector required>
       <div>Item 1</div>
       <div>Item 2</div>
       <div>Item 3</div>
     </plastik-selector>
```
## Multi-selection

 `plastik-selector` also allows for multi-selection. When multi-selection is enabled, more than one
 item can be selected at a time. Use `selectedValues` instead of `selected` when setting or getting
 the selected items. Just as with single selection, by default, item indexes are used, and if
 `attrForSelected` is specified, attribute values are used instead. `selectedValues` returns or sets
 an array of item indexes or attribute values. To enable multi-selection, set `multi` to true.
 
### Example
 ```html
     <plastik-selector multi selected-values="[0,2]">
       <div>Item 1</div>
       <div>Item 2</div>
       <div>Item 3</div>
     </plastik-selector>
```
## Reset items

When multi-selection is enabled, `plastik-selector` also allows the use of a reset item. The reset item
clears the selection state of the rest of the items when it is selected, and `plastik-selector` will
default to selecting the reset item when none others are selected. The reset item cannot be selected at
the same time as any other item, and there can only be one reset item per `plastik-selector`.

To enable use of a reset item, set `attrForReset` to the name of the attribute that will denote your
reset item. `attrForReset` cannot be used together with `required`: when `attrForReset` is set to any
value, the functionality provided by `required` is disabled.

### Example
```html
    <plastik-selector multi attr-for-reset="reset">
      <div reset>Any</div>
      <div>Small</div>
      <div>Medium</div>
      <div>Large</div>
    </plastik-selector>
```
## Styling

`plastik-selector` is not styled. Use the `iron-selected` CSS class to style the selected element.

### Example
```html
    <style>
      .iron-selected {
        background: #eee;
      }
    </style>
    ...
    <plastik-selector selected="0">
      <div>Item 1</div>
      <div>Item 2</div>
      <div>Item 3</div>
    </plastik-selector>
```
