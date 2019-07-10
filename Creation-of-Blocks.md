最简单的方块定义如下所示:
```json
{
  "type": "block:simple",
  "entries": [
    {
      "id": "my_first_block",
	  "creativeTab": "buildingBlocks"
    }
  ]
}
```

该属性定义该方块的**唯一**ID. ID必须全部小写, 且不得包含空格. ID只需要在你的模组中的命名空间中保持唯一性.

如果你现在启动游戏, 你会看见有一个方块在名为 **Building Blocks** 的创造模式标签页中.
然而它还缺少材质和模型. 为了给它添加材质和模型, 你需要创建一个 **方块状态** 文件. 这个文件告诉游戏什么模型和材质用于方块的什么状态. 该文件应该位于路径 `assets/mymod/blockstates` 中, 并且应该与块的 `id` 完全相同, 在我们的例子中这是`my_first_block.json`. 该文件的内容如下所示:

```json
{
  "variants": {
	"normal": {"model": "mymod:my_first_block"},
	"inventory": {"model": "mymod:my_first_block"}
  }
}
```

我们将因具有不同方块状态的但具有相同ID的方块称为 **变种**.只有一种变种的方块, 变种名称为 `normal`.  
方块变种 `normal` 告诉游戏世界上该方块的模型是什么. 在这种情况下, 模型文件的路径是 `assets/mymod/models/block/my_first_block.json`. 该文件的内容如下所示:
```json
{
    "parent": "block/cube_all",
    "textures": {
        "all": "mymod:blocks/my_first_block"
    }
}
```
这将使块看起来像一个常规立方体, 材质位于 `assets/mymod/textures/blocks/my_first_block.png` .

`inventory` 变种告诉游戏当方块在玩家的背包或者物品容器内时所呈现的材质和模型. 由于这种用途相当于给一个物品添加材质, 所以这个变种的材质路径在 `assets/mymod/models/item/my_first_block.json`. 该文件的内容如下所示:
```json
{
  "parent": "mymod:block/my_first_block",
  "display": {
    "thirdperson": {
      "rotation": [ 10, -45, 170 ],
      "translation": [ 0, 1.5, -2.75 ],
      "scale": [ 0.375, 0.375, 0.375 ]
    }
  }
}
```
这将使方块的物品形态看起来就像方块的模型.

.还有一件事: 如果你就这样, 在方块的物品形态的信息界面中, 其显示的名称是 `tile.my_first_block.name`. 这是方块的未本地化名称. 要为其添加本地化名称, 请将以下内容添加到`assets/mymod/lang/en_US.lang`(如果文件不存在则创建文件)：

```
tile.my_first_block.name=My First Block
```

该方块现在应该在游戏中显示其正确的本地化名称.
***
若你想了解更多关于方块的内容, 你可以使用[该链接](Blocks)跳转到响应页面.