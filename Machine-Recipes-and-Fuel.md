# Machine Recipes
Type name: __machineRecipe__

```json
{
  "input": [{"ore": "ingotGold", "amount": 4}, "minecraft:apple"],
  "output": [
    {
      "items": ["minecraft:gold_ingot", {"item": "minecraft:golden_apple", "chance": 0.25}],
      "fluids": ["water@500", "lava@500"],
      "weight": 1
    },
    {
      "items": ["minecraft:gold_ingot", {"item": "minecraft:golden_apple", "chance": 0.25}],
      "fluids": ["water@1000", "lava@1000"],
      "weight": 2
    }
  ],
  "inputFluid": ["water@500", "lava@500"],
  "outputFluid": ["examplefluid@1000"],
  "cookTime": 400,
  "recipeList": "mymod:machinerecipes"
}
```

* __input__: This is a list of RecipeInput defining the input items for the recipe.
* __output__: This is a list defining the output items and fluids for the recipe. Each entry in that list represents one possible outcome of the recipe. If the output for the recipe is just one simple item, you can also set this property to an ItemStack.
  * __items__: This is a list of ItemStack that define result items of an entry. An additional property that can be used is `chance`, which allows the item to only appear sometimes.
  * __fluids__: This is a list of FluidStack that define the result fluids of an entry.
  * __weight__: If the recipe has multiple outcomes, this property is used to make some outcomes more likely than others. Default value is 1.
* __inputFluid__: This is a list of fluid stacks defining the fluid input for the recipe.
* __cookTime__: This defines the number of ticks this recipe needs to finish. If 0, the cookTime of the machine is used instead. Default value is 0.
* __recipeList__: The list of recipes to add the recipe to.

## More Examples for Output

The output is always one gold ingot:
```json
{
  "output": "minecraft:gold_ingot"
}
```

The output is either a gold ingot or an iron ingot:
```json
{
  "output": [
    "minecraft:gold_ingot",
    "minecraft:iron_ingot"
  ]
}
```

The output is always an iron ingot and with a 50% chance an additional gold ingot:
```json
{
  "output": [
    {
      "items": [
        "minecraft:iron_ingot",
        {"item": "minecraft:gold_ingot", "chance": 0.5}      
      ]
    }
  ]
}
```

The output is always a gold ingot and an iron ingot:
```json
{
  "output": [
    {
      "items": ["minecraft:gold_ingot", "minecraft:iron_ingot"]
    }
  ]
}
```

The output is either a gold ingot or an iron ingot with the iron ingot to be twice as likely:
```json
{
  "output": [
    {
      "items": "minecraft:gold_ingot",
      "weight": 1
    },
    {
      "items": "minecraft:iron_ingot",
      "weight": 2
    }
  ]
}
```

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