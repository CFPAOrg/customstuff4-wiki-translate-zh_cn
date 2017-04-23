Type name: __toolTip__

```json
{  
	"item": "minecraft:coal",
	"text" : [ "This is coal.", "It burns" ],
	"clearExisting" : true,
	"mode" : "noshift"
}
```

* __item__: This is an ItemStack specifying the item to add the tool tip to.
* __text__: This is a list of strings, where each string is a line in the tool tip.
* __clearExisting__: Specifies whether the existing tool tip should be cleared. You can use this to replace an existing tool tip with your own. This is optional and defaults to _false_.
* __mode__: This defines when the tool tip is shown. There are 7 modes: all, ctrl, shift, alt, noctrl, noshift and noalt.

## Examples

The following two tool tips cause coal to have a "Press Shift for more" tool tip. Note that the first one has its mode set to _noshift_ and not _all_. Otherwise the "Press SHIFT" line would still show up when pressing SHIFT.
```json
{  
	"item": "minecraft:coal",
	"text" : [ "Press SHIFT for more text" ],
	"mode" : "noshift"
},
{  
	"item": "minecraft:coal",
	"text" : [ "This is coal.", "It burns." ],
	"mode" : "shift"
}
```
