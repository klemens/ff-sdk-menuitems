# Menuitems (Add-on SDK module)

The `Menuitem` API is a simple way to create
[Menuitems](https://developer.mozilla.org/en/XUL/PopupGuide/MenuItems), which
can perform an action when clicked and display state.

## Example

```js
// create menuitem for the File menu,
// and insert it before the 'Quit' menuitem
require("menuitems").Menuitem({
    id: "myextprefix-some-id",
    menuid: "menu_FilePopup",
    insertbefore: "menu_FileQuitItem",
    label: "Some label",
    image: self.data.url("icon.png"),
    className: 'pizazz',
    disabled: false,
    checked: false,
    onCommand: function() {
        // do something
    }
});
```

## Options

### id (String, *required*)
An id for the Menuitem, this should be namespaced.

### menuid (String, *required*)
The id of the parent node. (eg. `menu_ToolsPopup` or `menu_FilePopup`)

### insertbefore (String|Number)
The id of the element to insert the Menuitem before or `Menuitem.FIRST_CHILD`. The
Menuitem is appended to the end if `insertbefore` is not specified.

### label (String)
A label for the Menuitem.

### accesskey (String)
An accesskey for the Menuitem.

### image (String)
A image url for the Menuitem.

### className (String)
A default space delimited list of class names for the Menuitem.

### disabled (Boolean)
When a Menuitem is disabled it cannot be used, but is still displayed.

### checked (Boolean)
Displays a check beside the Menuitem.

### onCommand (Function)
A function that is invoked when the Menuitem is executed (clicked).

## Licence

This module by Erik Vold is licenced under Mozilla Public License (MPL) 2.0.
