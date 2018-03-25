To get started, you need to create a new folder in the mods directory of you minecraft installation. In that folder create a file called _cs4mod.json_ with the following content:
```json
{  
	"id": "mymod",
	"name": "My Mod",
	"version": "1.0.0"
}
```
Replace _mymod_ with the id for your mod. The id must only contain lowercase letters (a-z), numbers (0-9) and underscores.  
Replace _My Mod_ with the name for your mod.  
Replace _1.0.0_ with the version of your mod.

You can now start Minecraft, which will create the necessary files for your mod to work. Note that your mod will only appear in the mod list after the second start of Minecraft. There should now be a folder called _cs4mod_ next to _cs4mod.json_.  
That's it. You've set everything up.

To change the version of your mod, edit the _cs4mod.json_ file, delete the _cs4mod_ folder and start Minecraft. Make sure to not load a world before the second start of Minecraft as your mod will not be loaded until then.
……………………………………………………………………………………………………………………………………………………………………………………
为了开始，你需要在.minecraft/mods目录下建立一个新的文件夹，文件夹下建立一个叫cs4mod.json的文件，并在其中输入如下内容：
```json
{  
	"id": "mymod",
	"name": "My Mod",
	"version": "1.0.0"
}
```
将mymod替换成你自定义的mod名（引号保留），注意只允许小写字母，数字，和下划线“_”。
将My Mod替换成你想要的名字（可大写，一般与mymod相同即可）
1.0.0替换成你想要的mod版本。
接下来启动装了CS4的MC以安装必要的文件，注意第二次启动时，你自定义的mod才会出现在mod列表中，现在在cs4mod.json的旁边应该会出现一个叫cs4mod的文件夹。那就是了，你可以开始编写了。
如果要更新自定义mod的版本，编辑cs4mod.json，删除cs4mod文件夹，并重启MC。确保在第二次启动前不要加载世界，因为在此期间你的mod不会被加载。
