Type name: __guiModifier__

```json
{  
	"gui": "mainMenu",
	"labels" : [
		{
			"alignX" : "left",
			"alignY" : "top",
			"offsetX" : 3,
			"offsetY" : [ "10%", 3 ],
			"text" : "The text for the label",
			"dropShadow" : true
		}
	],
	"removeButtons" : [ 0, 5, 7 ],
	"editButtons" : [
		{
			"buttonId" : 0,
			"alignX" : "left",
			"alignY" : "top",
			"offsetX" : 3,
			"offsetY" : [ "10%", 3 ],
			"text" : "New button text",
			"width" : "12.3%",
			"height" : 20
		}
	]
}
```

* __gui__: The name of the GUI that is being modified.
* __labels__: This is a list of labels that are being added to the GUI.
	* __alignX__: This defines the horizontal alignment of the label. It can be left, right or center. This is optional and defaults to left.
	* __alignY__: This defines the vertical alignment of the label. It can be top, bottom or center. This is optional and defaults to top.
	* __offsetX__: This defines the horizontal offset from the positioned specified with alignX. This can be an absolute value, a relative value or both. This is optional and defaults to 0.
	* __offsetY__: This defines the horizontal offset from the positioned specified with alignY. This can be an absolute value, a relative value or both. This is optional and defaults to 0.
	* __text__: This defines the text that is shown.
	* __dropShadow__: This defines whether the text should be drawn with a drop shadow. This is optional and defaults to true.
* __removeButtons__: This is a list of integers, where each integer specifies the id of a button that is being removed from the GUI.
* __editButtons__: This is a list of buttons that are being modified. 
	* __buttonId__: This defines the id of the button that is being modified.
	* __alignX, alignY__: Same as for labels.
	* __offsetX, offsetY__: Same as for labels. If these are omitted, the position of the button is not changed.
	* __width__: The new width for the button. This can be an absolute value, a relative value or both. If omitted, the width is not changed.
	* __height__: The new height for the button. This can be an absolute value, a relative value or both. If omitted, the height is not changed.
	* __text__: The new text for the button. If omitted, the text is not changed.

# Available GUIs
* mainMenu
* ingameMenu
* options
* multiplayer
* connecting
* downloadTerrain
* gameOver

## Examples

The following will add a "Custom Stuff 4" label in the bottom-left corner, remove the "Open To LAN" button and move the "Return to Game" button to its place changing the text to "Close this GUI".
```json
{
	"gui" : "ingameMenu",
	"labels" : [
		{
			"offsetX" : 2,
			"offsetY" : -2,
			"alignX" : "left",
			"alignY" : "bottom",
			"text" : "Custom Stuff 4"
		}
	],
	"editButtons" : [
		{
			"buttonId" : 4,
			"text" : "Close this GUI",
			"offsetY":  ["25%", 8 ]
		}
	],
	"removeButtons" : [ 7 ]
}
```
