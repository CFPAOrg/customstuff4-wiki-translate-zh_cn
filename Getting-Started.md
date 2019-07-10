首先，您需要在 `.minecraft/mods` 中创建一个新文件夹. 在该文件夹中, 创建名为 `cs4mod.json` 的文件并填入相应内容:
```json
{  
	"id": "mymod",
	"name": "My Mod",
	"version": "1.0.0"
}
```
将 `mymod` 替换为你的mod的id, id必须只包含小写字母(a-z), 数字(0-9)和下划线.
将 `My Mod` 替换为你的mod的名称.
将 `1.0.0` 替换为你的mod版本.

你现在可以启动Minecraft, 并将为你的mod创建必要的文件. 请注意, 你的mod只会在第二次启动Minecraft后才会出现在mod列表中. 现在应该在 `cs4mod.json` 旁有一个名为 `cs4mod` 的文件夹.  
完事了, 你已经把一切都搞定了.

要更改mod的版本, 请编辑 `cs4mod.json` 文件, 删除 `cs4mod` 文件夹并启动Minecraft. 确保在第二次启动Minecraft之前不加载世界, 因为在此之前你的mod不会加载.