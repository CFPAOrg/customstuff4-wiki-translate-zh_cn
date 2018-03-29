In Minecraft 1.12 and up recipes for the vanilla crafting table are added with minecrafts own json files. Removal of recipes is currently disabled. To damage an item in a recipe you can use the __customstuff4:damageable_shaped__ and __customstuff4:damageable_shapeless__ recipe types like this: https://github.com/cubex2/customstuff4/tree/master/examplemod/assets/cs4examplemod/recipes

# Shaped Recipes

Type name: __shapedRecipe__

```json
{
  "shape": ["SS", "D "],
  "items": {
    "S": "minecraft:sword_diamond@all",
    "D": "ore:blockDiamond"
  },
  "damage": {
    "S": 5
  },
  "result": {
    "item": "minecraft:obsidian",
    "amount": 3
  },
  "mirrored": false,
  "remove": false,
  "recipeList": "mymod:myrecipes"
}
```
	
* __shape__: This is a list of strings. Each string is row in the recipe and each letter in the string one item. Every string has to have the same length and must be between 1 and 3 letters long. There must not be more than 3 strings.

* __items__: Together with _shape_, this defines the input for the recipe. This maps the letters used in _shape_ to a RecipeInput. If you want to have empty spots in the recipe, just don't define an item for that letter. You may use "all" for metadata. Specifying _nbt_ here has no effect.
* __damage__: Specifies for each item if it should be damaged instead of used up. Default is 0 which means item is used up.
* __result__: This is an ItemStack defining the result of the recipe.

* __mirrored__: This is either _true_ or _false_ and specifies whether the accepts the mirrored version of the shape. This is optional and defaults to _true_.
* __remove__: If true, the recipe will be removed instead of added. If true, either result or shape and items can be omitted which will remove all recipe that match the input or result. Default value is false.
* __recipeList__: The list to add or remove the recipe from.

# Shapeless Recipes

Type name: __shapelessRecipe__

```json
{
  "items": [
    "minecraft:sword_diamond@all",
    "oreclass:stickWood"
  ],
  "damage": [5, 0],
  "result": {
    "item": "minecraft:obsidian",
    "amount": 3
  },
  "remove": false,
  "recipeList": "mymod:myrecipes"
}
```
	
* __items__: This is a list of RecipeInput and defines the items that are required for the recipe. You may use "all" for metadata. Specifying _nbt_ here has no effect.
* __damage__: Specifies for each item if it should be damaged or used up where 0 means it will be used and everything greater will just damage the item. You can either not define this at all or for every input item.
* __result__: This is an ItemStack defining the result of the recipe.
* __remove__: If true, the recipe will be removed instead of added. If true, either result or items can be omitted which will remove all recipe that match the input or result. Default value is false.
* __recipeList__: The list to add or remove the recipe from.