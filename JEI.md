# Machine and Crafting Recipes
Type names: __jei:machineRecipe__, __jei:craftingRecipe__

These two add support for a machine or crafting recipe list to JEI.

```json
{
  "recipeList": "cs4examplemod:machine",
  "gui": "cs4examplemod:machine",
  "tileEntity": "cs4examplemod:machine",
  "bgX": 37,
  "bgY": 16,
  "bgWidth": 126,
  "bgHeight": 54,
  "icon": "cs4examplemod:machine",
  "title": "Machine Recipes",
  "recipeAreaX": 80,
  "recipeAreaY": 35,
  "recipeAreaWidth": 22,
  "recipeAreaHeight": 15,
  "transferButtonX": 119,
  "transferButtonY": 57
}
```

* __recipeList__: This is a ResourceLocation defining what list of recipes is being used.

* __gui__: This is a ResourceLocation defining the gui of the machine or crafting table.

* __tileEntity__: This is a ResourceLocation defining the tile entity of the machine or crafting table.

* __bgX__, __bgY__, __bgWidth__, __bgHeight__: These define what part of the background texture from the gui is shown in the JEI gui. The area should at least contain all the important slots for the recipe.

* __icon__: This is a ItemStack that defines what item is used as the icon.

* __title__: The title that is being used in the JEI gui.

* __recipeAreaX__, __recipeAreaY__, __recipeAreaWidth__, __recipeAreaHeight__: These define where in the gui you can click to open the JEI gui that shows the recipes.

* __transferButtonX__, __transferButtonY__: If the default position of the transfer button doesn't fit, use these to position the button. The values are relative to the machine/crafting gui background.

# Item Descriptions
Type name: __jei:description__

This will create a description page in the JEI gui.

```json
{
  "items": ["cs4examplemod:crafter"],
  "desc": ["cs4examplemod.crafter.jei.desc"]
}
```

* __items__: This is a list of ItemStack defining what items to add the description to.

* __desc__: This is a list of description keys where each entry will be on a new line. You can use \n inside an entry to create a new line.
