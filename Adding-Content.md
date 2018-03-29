To add content, you'll have to create a new file called _main.json_. This file contains everything that is being added to the game. However you can outsource anything to another file.
Every json file consists of named lists, where each entry in these lists adds one or more things of the same type, for example shaped recipes.

For a simple smelting recipe the file might look like this:

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
	
The name of the list, _content_ here, is completely arbitrary and just adds a little more structure. You could have a list for recipes and another one for fuel.  
That's all you need to do add some content.

If you want to use multiple files, for example to have recipes in its own file, you can do this:

```json
{
  "content": [
    {
      "file": "recipes.json"
    }
  ]
}
```
	
Files loaded that way work exactly the same as _main.json_. This means you can a file load another file which then itself loads some files. For example, you can let _recipes.json_ load _crafting\_recipes.json_ and _smelting\_recipes.json_.

You can also add conditions to a content entry to only load that content if the conditions are met. You can, for example, only add certain recipes if a specific mod is loaded:

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
	
This works for both _file_ and _entries_.  
The content is only loaded if all conditions are met. In the example above, _chesttransporter_ has to be loaded and _morefurnaces_ must not.