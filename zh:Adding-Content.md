为添加各种游戏要素（合成表，多方块结构等），你需要建立一个新的文件叫做“main.json”，这个文件包含了你所有添加到游戏中的东西，当然你也可以把这些内容放到另一个文件中。
每一个json文件由被命名的表单构成，你可以在表单中添加同一类型（type）的修改（例如有序合成）。
一个简单的合成文件长得应该像这样：
```json
{
  "content": [
    {
      "type": "shapedRecipe",（类型：有序合成）
      "entries": [
        {
          "shape": ["AA", "BX"],（shape指的是合成表顺序）
          "items": {
            "A": "minecraft:coal",（minecraft：coal指煤）
            "B": "minecraft:diamond"
          },
          "result": "minecraft:apple"（合成结果）
        }
      ]
    }
  ]
}（从第一个大括号到最后一个大括号即为一个表单）
```
表单名也就是那个“content”，完全是瞎取名，只是添加一点结构性而已。你也可以在同一个文件中写一个用来合成的表单，也可以写一个注册燃料的。
以上就是你要添加一个要素所要做的事。
如果你想要多个文件，例如将合成表放入它自己专属的文件（例如recipes.json）中，你可以像这样增加一个file项：
```json
{
  "content": [
    {
      "file": "recipes.json"
    }
  ]
}
```
其他json文件加载的机制和main.json是一样的，这意味着你可以搞“一拖几”的文件，例如你可以让“recipes.json”加载“crafting\_recipes.json”和“smelting\_recipes.json”。
你也可以向表单中添加前置条件，只有当条件满足时，才加载这一表单代表的要素。例如，你可以添加特定mod被加载时的特定合成：

```json
{
  "content": [
    {
      "file": "recipes.json",
      "requireModsLoaded": ["chesttransporter"],（有chest transpoter，搬箱器mod时该要素被加载）
      "requireModsNotLoaded": ["morefurnaces"],（没有more furnaces，更多熔炉mods时该要素被加载）
    }
  ]
}

这一条件对“file”和“entries”这两项均有效，在示例中，一定需要加载搬箱器mod，且一定不能加载更多熔炉mod，否则该合成无效。