# Shaped Recipes

Type name: __shapedRecipe__

```json
{
  "shape": ["SS", "DX"],
  "items": {
    "S": "minecraft:stone@all",
    "D": "ore:blockDiamond"
  },
  "result": {
    "item": "minecraft:obsidian",
    "amount": 3
  },
  "mirrored": false
}
```
	
* __shape__: This is a list of strings. Each string is row in the recipe and each letter in the string one item. Every string has to have the same length and must be between 1 and 3 letters long. There must not be more than 3 strings.

* __items__: Together with _shape_, this defines the input for the recipe. This maps the letters used in _shape_ to a RecipeInput. If you want to have empty spots in the recipe, just don't define an item for that letter. You may use "all" for metadata. Specifying _nbt_ here has no effect.

* __result__: This is an ItemStack defining the result of the recipe.

* __mirrored__: This is either _true_ or _false_ and specifies whether the accepts the mirrored version of the shape. This is optional and defaults to _true_.

# Shapeless Recipes

Type name: __shapelessRecipe__

```json
{
  "items": [
    "minecraft:stone@all",
    "oreclass:stickWood"
  ],
  "result": {
    "item": "minecraft:obsidian",
    "amount": 3
  }
}
```
	
* __items__: This is a list of RecipeInput and defines the items that are required for the recipe. You may use "all" for metadata. Specifying _nbt_ here has no effect.

* __result__: This is an ItemStack defining the result of the recipe.