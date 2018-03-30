In its most simple form, the definition of a block looks like this:
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

The `id` property defines the internal name of the block. It has to be unique in your mod.

If you start the game now, you should see the block in the **Building Blocks** creative tab and can already place it.
However it still uses the missing texture and model. To fix this, you need to create a **Block State** file. This file tells the game what model and thus texture to use
for what state of the block. The file should be located in `assets/mymod/blockstates` and should have the exact same name as the `id` of the block, in our case this is `my_first_block.json`. The contents of the file might look like this:

```json
{
  "variants": {
	"normal": {"model": "mymod:my_first_block"},
	"inventory": {"model": "mymod:my_first_block"}
  }
}
```

The `normal` variant tells the game what model is being for the block in the world. In this case the model file is `assets/mymod/models/block/my_first_block.json`. The contents of that file might look like this:
```json
{
    "parent": "block/cube_all",
    "textures": {
        "all": "mymod:blocks/my_first_block"
    }
}
```
This will make the block look like a regular cube with the texture located at `assets/mymod/textures/blocks/my_first_block.png`.

The `inventory` variant tells the game what model is being used if the block is an item in an inventory. Since this variant applies to the block's item, the file is `assets/mymod/models/item/my_first_block.json`. The contents of that file might look like this:
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
This will make the block's item look like the block's model.

There's one last thing missing: if you hover of the block in the inventory, the displayed name is `tile.my_first_block.name`. This is the unlocalized name of the block. To add a localized name for it, add the following line to `assets/mymod/lang/en_US.lang` (create it if it doesn't exist):

```
tile.my_first_block.name=My First Block
```

The block should now display its proper localized name in the game.
***
More information about blocks can be found [here](Blocks).