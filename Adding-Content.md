为了添加一个条目, 你需要创建一个叫做 _main.json_ 的文件. 此文件包含所有添加到游戏中的内容. 虽然你也可以把其他文件中所描述的条目内容添加到游戏里.
每个json文件都包含具名列表, 其中这些列表中的每个条目都添加了一个或多个相同类型的内容, 例如有序合成台配方.

下面所声明的代码块内便描述了一个有序合成台配方:

```json
{
  "content": [
    {
      "type": "smeltingRecipe",
      "entries": [
        {
          "input": "minecraft:stone",
          "result": "minecraft:obsidian"
        }
      ]
    }
  ]
}
```
	
这个叫 _content_ 的列表, 内容是完全随意的, 也只是添加了一点点结构. 你也可以构筑一个合成配方或燃料的列表.  
这一切都只需要你添加一些 _条目_ .

如果要使用多个文件, 让他们各司其职, 可以这样做:

```json
{
  "content": [
    {
      "file": "recipes.json"
    }
  ]
}
```
	
以这种方式加载的文件与 _main.json_ 完全相同. 这意味着你可以加载另一个文件然后让它自己加载另一些文件.
举例说: 你可以让 _recipes.json_ 加载 _crafting\_recipes.json_ 和 _smelting\_recipes.json_ 文件.

你也可以设定在一些特殊条件被满足的情况下加载响应条目. 举例, 该条目会在模组 `chesttransporter` 被安装和模组 `morefurnaces` 没有被安装时加载.

```json
{
  "content": [
    {
      "file": "recipes.json",
      "requireModsLoaded": ["chesttransporter"],
      "requireModsNotLoaded": ["morefurnaces"],
    }
  ]
}
```
	
这同时适用于文件和条目.  

当你设置的所有条件 **全部** 被满足时, 这条条目才会生效.

***
了解更多:
* [[方块的创建]]