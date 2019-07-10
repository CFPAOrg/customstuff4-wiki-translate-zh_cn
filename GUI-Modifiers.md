类名: __guiModifier__

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
			"dropShadow" : true,
			"color": "white"
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

* __gui__: 原GUI的名称
* __labels__: 添加到GUI的标签列表.
	* __alignX__: 该属性定义了标签的水平对齐方式. 它可以是 `left`(向左), `right`(向右) 或 `center`(居中) . 这是可选项, 默认为 `left`(居左).
	* __alignY__: 该属性定义了标签的垂直对齐方式. 它可以是 `top`(向上), `bottom`(向下) 或 `center`(居中). 这是可选项, 默认为 `top`(向上).
	* __offsetX__: 该属性定义了使用 `alignX` 指定的位置的水平偏移量. 这可以是绝对值, 也可以是相对值, 两者皆可. 这是可选项, 默认为 `0`.
	* __offsetY__: 该属性定义了使用 `alignY` 指定的位置的垂直偏移量. 可以是绝对值, 也可以是相对值, 两者皆可. 这是可选项, 默认为 `0`.
	* __text__: 该属性定义了将会显示的文本。
	* __dropShadow__: 该属性定义了是否应该使用投影渲染文本. 这是可选项, 默认为 `true`.
	* __color__: 该属性定义了文本的颜色. 默认值为 `white`(白色).
* __removeButtons__: 这是一个整数列表, 其中每个整数指定从GUI中删除的按钮的ID.
* __editButtons__: 这是用于修改GUI中已存在的按钮的列表.
	* __buttonId__: 于 `removeButtons` 中定义了的按钮ID
	* __alignX, alignY__: 和标签的那个一样
	* __offsetX, offsetY__: 和标签的那个一样, 但是如果省略该选项, 按钮的位置不会改变.
	* __width__: 按钮的宽度(长度). 可以是绝对值, 也可以是相对值, 两者皆可. 如果省略, 按钮的宽度(长度)不会改变.
	* __height__: 按钮的高度. 可以是绝对值, 也可以是相对值, 两者皆可. 如果省略, 按钮的高度不会改变.
	* __text__: 显示在按钮内部的文本, 如果省略, 按钮内部显示的文本不会改变.

# 原版中可用的GUI
* mainMenu
* ingameMenu
* options
* multiplayer
* connecting
* downloadTerrain
* gameOver

## 示例

以下条目所表示的GUI将在左下角添加 `Custom Stuff 4` 标签，删除 `Open To LAN` 按钮并将 `Return to Game` 按钮移动到其位置, 将文本更改为 `Close this GUI`.
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
