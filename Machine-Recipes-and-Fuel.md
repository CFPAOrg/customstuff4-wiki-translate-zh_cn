# Machine Recipes
Type name: __machineRecipe__

```json
{
  "input": [{"ore": "ingotGold", "amount": 4}, "minecraft:apple"],
  "output": ["minecraft:gold_ingot", {"item": "minecraft:golden_apple", "chance": 0.25}],
  "inputFluid": ["water@500", "lava@500"],
  "outputFluid": ["examplefluid@1000"],
  "cookTime": 400,
  "recipeList": "mymod:machinerecipes"
}
```

* __input__: This is a list of RecipeInput defining the input items for the recipe.
* __output__: This is a list defining the output items for the recipe. Each entry is a ItemStack with the possibility to add a chance attribute.
* __inputFluid__: This is a list of fluid stacks defining the fluid input for the recipe.
* __outputFluid__: This is a list of fluid stacks defining the fluid output for the recipe.
* __cookTime__: This defines the number of ticks this recipe needs to finish. If 0, the cookTime of the machine is used instead. Default value is 0.
* __recipeList__: The list of recipes to add the recipe to.

# Machine Fuel
Type name: __machineFuel__

```json
{
	"items": ["ore:stickWood", "minecraft:coal"],
	"burnTime": 200,
	"fuelList": "mymod:machinefuel"
}
```

* __items__: This is a list of RecipeInput defining the items that can be burned together.
* __burnTime__: The number of ticks the items burn in a machine.
* __fuelList__: This list to add the fuel to.