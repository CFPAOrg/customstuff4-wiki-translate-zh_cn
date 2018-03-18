# All Blocks
Some attributes are used by all types of blocks:

```json
{
	"id" : "myblock",
	"material" : "ground",
	"itemModel" : "mymod:myitemmodel",
	"creativeTab" : "redstone",
	"hardness" : 2.5,
	"resistance" : 5.5,
	"soundType" : "metal",
	"maxStack" : 16,
	"opacity" : 128,
	"light" : 7,
	"flammability" : 50,
	"fireSpreadSpeed" : 10,
	"isFireSource" : false,
	"isWood" : false,
	"canSustainLeaves" : false,
	"isBeaconBase" : false,
	"enchantPowerBonus" : 1.5,
	"expDrop" : [0, 1],
	"information" : [ "First line", "Second line"],
	"tileEntity": "mymod:mytileentity",
	"gui": "mymod:mygui",
	"drop": ["minecraft:dirt", {"item" : "minecraft:stone", "amount": [1,4] } ],
	"isFullCube": false,
	"isOpaqueCube": false,
	"isBurning": false,
	"bounds": { "cube": 0.5, "offset": [0.25, 0.25, 0.25] },
	"slectionBounds": { "cube": 1 },
	"collisionBounds": { "cube": 0.5, "offset": [0.25, 0.25, 0.25] },
	"tint": "foliage",
	"itemTint": "foliageBasic",
	"renderLayer": "solid",
	"canSilkHarvest": false,
	"harvestTool": "axe",
	"harvestLevel": 3,
	"canPlaceOnCeiling": true,
	"canPlaceOnFloor": true,
	"canPlaceOnSides": true,
	"sustainedPlants": "Crop",
	"burnTime": 100,
	"slipperiness": 0.6,
	"pathNodeType": "blocked",
	"isWeb": true
}
```

* __id__: This is the unique id of the block. This is used to reference the block in recipes or in the lang file. This has to be all lowercase and must not contain spaces. It only has to be unique in your mod. If your mod id is _mymod_ and the item id is _myblock_, you reference the item with _mymod:block_. The block state files is then located in _assets/mymod/blockstates/myblock.json_. If the block has an item associated with it as most blocks do, that item has the same id.

* __material__: This is the material of the block. The material defines different default properties for the block such as if it is translucent or if it requires a tool to mine. The default value is _ground_.

* __itemModel__: This defines the model file that is being used for the item of the block. In the example above the file is located in _assets/mymod/models/item/myitemmodel.json_ or _assets/mymod/blockstates/myitemmodel.json_. You can also use the model of another mod or minecraft itself. Supports metadata subtypes. Default value is "[modid:blockid]". 

* __creativeTab__: This defines the creative tab that the item of the block appears in. Omit to make it not appear in any tab. Supports metadata subtypes.

* __hardness__: This defines how long it takes to break the block. Supports metadata subtypes. The default value is 1.0. 

* __resistance__: This defines the resistance against explosions. Supports metadata subtypes. The default value is 0.0.

* __soundType__: This defines the sound that is being played when the block is being walked on, breaked or placed. Supports metadata subtypes. The default value is stone.

* __maxStack__: This defines the maximum number of items in one stack. This has to be between 1 and 64. Supports metadata subtypes. The default value is 64.

* __opacity__: This defines the light opacity. This has to between 0 and 255 where 0 means all light goes through the block and 255 means none does. Supports metadata subtypes. The default value is 255.

* __light__: This defines how much light the block is emitting. This has to be between 0 and 15, where 0 means no light and 15 means as much light as possible. Supports metadata subtypes. The default value is 0.

* __flammability__: This defines the chance that fire will spread and consume the block. This has to be between 0 and 100, where 0 is 0% chance and 100 a 100% chance. Supports metadata subtypes. The default value is 0.

* __fireSpreadSpeed__: This defines how fast fire will spread around the block. Higher values mean higher speed. Supports metadata subtypes. The default value is 0.

* __isFireSource__: This defines whether fire indefinitely burns on the block. Supports metadata subtypes. The default value is false.

* __isWood__: This defines whether the block is wood. Supports metadata subtypes. The default value is false.

* __canSustainLeaves__: This defines whether leaves decay near the block. Supports metadata subtypes. The default value is false.

* __isBeaconBase__: This defines whether the block can be used as a base for the beacon. Supports metadata subtypes. The default value is false.

* __enchantPowerBonus__: This defines the amount of enchanting power this block can provide to an enchanting table. Supports metadata subtypes. The default value is 0.0.

* __expDrop__: This defines the amount of exp dropped when breaking the block. You can define it like this: `5` or like this: `[1, 5]`. The first one will always drop 5 exp, the second one drops a random amount between 1 and 5. Supports metadata subtypes. The default value is 0.

* __information__: This defines additional lines of information below the name of the item in the inventory. Supports metadata subtypes.

* __tileEntity__: This is a ResourceLocation defining what tile entity the block is using. Use the id of the tile entity together with the mod id. Supports metadata subtypes. Default is no tile entity.

* __gui__: This is a ResourceLocation defining what gui is being opened when right-clicking the block. Use the id of the gui together with the mod id. Supports metadata subtypes. Default is no gui.

* __drop__: This is either one or multiple BlockDrop. To make the block not drop anything use `minecraft:air`. If omitted, the block will just drop itself. Supports metadata subtypes.

* __isFullCube__: Defines whether this block is a full cube. If false, connected sides of neighbouring blocks will be rendered. Supports metadata subtypes.

* __isOpaqueCube__: Defines whether this block is opaque. If the block is not a full cube or has transparent textures, this should be set to false. Supports metadata subtypes.

* __isBurning__: Defines whether this block should set entities on fire when they get in contact with the block. Note that the collision bounding box needs to be slightly smaller than a full cube for this to work. Supports metadata subtypes.

* __bounds__:  This is a BoundingBox. Defines the bounding box of the block. This box is used to check if you mouse over the block. If not specified aswell, this will also set the selection and collision bounding box. Supports metadata subtypes.

* __selectionBounds__: This is a BoundingBox. Defines the highlighted wireframe box that is shown when you mouse over the block. Supports metadata subtypes.

* __collisionBounds__:  This is a BoundingBox. Defines the box that entities actually collide with. Supports metadata subtypes.

* __tint__: Defines the tint that is applied to the block in the world. These is either a color or one of foliage, grass or water which will tint the block depending on the biome. Supports metadata subtypes.

* __itemTint__: Defines the tint of item associated with the block. This is a color. Supports metadata subtypes.

* __renderLayer__: This defines block render layer and should depend on the texture of the block. If the texture has no transparent parts use `solid` or omit it. If it has transparent parts use either `cutout` or `mippedCutout` where ther latter will make the texture to be mip-mapped. If the texture has semi-transparent parts use `translucent`.

* __canSilkHarvest__: Defines whether the block can be silk harvested. Default value is true. Supports metadata subtypes.

* __harvestTool__, __harvestLevel__: Defines the tool and level that is required to effectively harvest the block. Note that if the block's material is iron or rock it will always be harvestable by pickaxes. Support metadata subtypes.

* __sustainedPlants__: Defines what plants are sustained by the block. You can use one or multiple of: Plains, Desert, Beach, Cave, Water, Nether, Crop. Supports metadata subtypes.

* __canPlaceOnFloor__, __canPlaceOnCeiling__, __canPlaceOnSides__: Defines whether the block can placed into the world by clicking the top, bottom or horizontal sides of another block.

* __burnTime__: Defines the number of ticks that the block provides fuel for a furnace. -1 lets the furnace decide on this, for example if the block's material is wood. Supports metadata subtypes. Default value is -1.

* __slipperiness__: Defines how much velocity is maintained while moving on top of the block. Supports metadata subtypes. Default value is 0.6.

* __pathNodeType__: Defines how mobs see the block when pathfinding. Valid values: blocked, open, walkable, trapdoor, fence, lava, water, rail, dangerFire, damageFire, dangerCactus, damageCactus, dangerOther, damageOther, doorOpen, doorWoodClosed, doorIronClosed. Omitting this will use the block's default. Supports metadata subtypes.

* __isWeb__: If set to true, the block will make entities move very slowly while inside the block just like the regular web block. Supports metadata subtypes. Default value if false.

# Metadata Subtypes
Some block types support metadata subtypes. That means the block can have different models, names or other things depending on their metadata value.  
If a block type supports metadata subtypes, you can enable it by providing the _subtypes_ attribute:

```json
{
	"subtypes" : [ 0, 1, 5 ]
}
```
This will make the item have subtypes for metadata values 0, 1 and 5. You should always have a 0 in their. Depending on the type of the block, you can use up to 16 subtypes (0 to 15).

You can now define attribute values for each of those metadata values provided that the attribute is supporting it:

```json
{
	"itemModel" : {
		"0" : "mymod:myitem_0",
		"1" : "mymod:myitem_1",
		"5" : "mymod:myitem_5"
	}
}
```

You can still define the attribute like this:

```json
{
	"itemModel" : "mymod:myitem"
}
```

This will set the value for all subtypes.

# Lang File
The lang files are located in _assets/themodid/lang_.

The lang file entry for a block without subtypes looks like this:

```
tile.themodid.theblockid.name=The Localized Name
```

And for a block with subtypes:

```
tile.themodid.theblockid.0.name=Subtype 0
tile.themodid.theblockid.1.name=Subtype 1
tile.themodid.theblockid.5.name=Subtype 5
```

# Materials
The following materials can be used:

* air
* cactus
* circuits
* clay
* cloth
* craftedSnow
* fire
* glass
* grass
* ground
* ice
* iron
* lava
* leaves
* plants
* pumpkin
* redstoneLight
* rock
* sand
* snow
* sponge
* tnt
* vine
* water
* wood

# Sound Types
The following sound types can be used.

* anvil
* cloth
* glass
* grass
* gravel
* ladder
* metal
* sand
* slime
* snow
* stone
* wood

# Creative Tabs

* brewing
* buildingBlocks
* combat
* decorations
* food
* inventory
* materials
* misc
* redstone
* search
* tools
* transportation

# Block States
The blockstate file defines what model the block uses depending on its state. For example the metadata subtype is a state. A simple blockstate file for a block using subtypes might look like this:

```json
{
  "variants": {
	"subtype=subtype0": {"model": "firstpack:sensor_iron"},
	"subtype=subtype1": {"model": "firstpack:sensor_gold"}
  }
}
```

For more information about block states, you might look here: http://minecraft.gamepedia.com/Model#Block_states

# Simple
Type name: __block:simple__

This block has no special functionality, like stone or dirt. It supports all 16 metadata subtypes. There are no additional attributes for this block.

Block state properties: subtype.

# Orientable
There are 3 different orientable blocks: vertical, horizontal and directional. All of them have one additional attribute:

```json
{
  "faceBySide" : true
}
```

* __faceBySide__: This defines whether the facing of the block should be determined by the clicked side instead of where the player is looking. If the block can't face in the direction of the clicked side, the facing is still determined on the direction the player is looking at. Supports metadata subtypes. The default value is false.

### Vertical
Type name: __block:orientable:vertical__

This block can face only up and down. It supports metadata subtypes 0 to 7.

Block state properties: facing and subtype. Facing can either be _up_ or _down_.

### Horizontal
Type name: __block:orientable:horizontal__

This block can face to north, south, east and west. It supports metadata subtypes 0 to 3.

Block state properties: facing and subtype. Facing can be _north_, _south_, _east_ and _west_.

### Directional
Type name: __block:orientable:directional__

This block can face in all directions. It supports metadata subtypes 0 and 1.

Block state properties: facing and subtype. Facing can be _up_, _down_, _north_, _south_, _east_ and _west_.

# Fence
Type name: __block:fence__

This is a fence block. It supports all 16 metadata subtypes. There are no additional attributes for this block.

Block state properties: subtype.

# Stairs
Type name: __block:stairs__

This is a stairs block. It does not support metadata subtypes. It has one additional attribute:

```json
{
  "modelState": {
    "block": "minecraft:log",
    "properties": {
      "variant": "spruce"
    }
  }
}
```

* __modelState__: This is a BlockState defining which block this stair is made from. This state will define some properties of the stair, such as the material.

Block state properties: facing, half and shape. Facing can be _north_, _south_, _east_ and _west_. Half can be _bottom_ and _top_. Shape can be _straight_, _outer_right_, _outer_left_, _inner_right_ and _inner_left_.

# Slab
Type name: __block:slab__

This is a half slab lock. It supports metadata subtypes 0 to 7. It has one additional attribute:

```json
{
  "doubleSlab" : {
	  "block": "minecraft:log",
	  "properties": "variant=spruce"
  }
}
```

* __doubleSlab__: This is a BlockState defining what two half slabs are being combined to. Supports metadata subtypes. If omitted, slabs can't be combined.

Block state properties: subtype and half. Half can be either _top_ or _bottom_.

# Fluid
Type name: __block:fluid__

This is a fluid block. The id of this block will also be the id of the fluid (without the mod prefix), so don't use something like water or lava as those already exist. It does not support metadata subtypes. It has the following additional attributes:

```json
{
  "density": 1000,
  "temperature": 300,
  "viscosity": 1000,
  "flowLength": 8,
  "isGaseous": false,
  "canCreateSource":  false,
  "addUniversalBucket": true,
  "texStill": "cs4examplemod:blocks/fluid_still",
  "texFlowing": "cs4examplemod:blocks/fluid_flow"
}
```

* __density__: Defines the density of the fluid. Negative density indicates that the fluid is lighter than air. Default value is 1000.
* __temperature__: Defines the temperature of the fluid in Kelvin. Default value is 300.
* __viscosity__: Defines the viscosity ("thickness") of the fluid. Higher value means that a fluid flows more slowly, lower value means more quickly. Default values is 1000.
* __flowLength__: Defines how far away the fluid flows from a source block. Value should be between 0 and 15. Default value is 8.
* __isGaseous__: Indicates if the fluid is gaseous. Default value is false.
* __canCreateSource__: Defines whether two source blocks can create another source block, like water. Default value is false.
* __addUniversalBucket__: Defines whether the fluid can be picked up by forge's universal bucket. Default value is true.
* __texStill__, __texFlowing__: The still and flowing textures for the fluid.

The block state file for the fluid should look like this (replace examplefluid with the id of your fluid):

```json
{
    "forge_marker": 1,
    "defaults": {
    	"model": "forge:fluid",
        "custom": { "fluid": "examplefluid" }
    },
    "variants": {
    	"level": {
        	"0": {"model": "forge:fluid"},
        	"1": {"model": "forge:fluid"},
        	"2": {"model": "forge:fluid"},
        	"3": {"model": "forge:fluid"},
        	"4": {"model": "forge:fluid"},
        	"5": {"model": "forge:fluid"},
        	"6": {"model": "forge:fluid"},
        	"7": {"model": "forge:fluid"},
        	"8": {"model": "forge:fluid"},
        	"9": {"model": "forge:fluid"},
        	"10": {"model": "forge:fluid"},
        	"11": {"model": "forge:fluid"},
        	"12": {"model": "forge:fluid"},
        	"13": {"model": "forge:fluid"},
        	"14": {"model": "forge:fluid"},
        	"15": {"model": "forge:fluid"}
        }
    }
}
```

# Carpet
Type name: __block:carpet__

This is a carpet block. It supports all 16 metadata subtypes. There are no additional attributes for this block.

Block state properties: subtype.

# Snow
Type name: __block:snow__

This is a layered snow block. It does not support metadata subtypes. It has the following additional attributes:

```json
{
  "snowball": "minecraft:snowball",
  "maxLight": 15
}
```

* __snowball__: If specified, this ItemStack will be dropped once for each layer plus one (1 layer drops 2, 2 layers drop 3).
* __maxLight__: If the block's light level is above the provided value, the block will disappear. Setting this to 15 will make the block not disappear at all. Default value is 11.

Block state properties: layers. It has values between 1 and 8, including both.

# Crops
Type name: __block:crops__

This is a crops block like carrots or potatoes. It does not support metadata subtypes. It has the following additional attributes:

```json
{
  "maxAge": 3,
  "growthFactor": 1.5,
  "heights": [0.1, 0.3, 0.6, 1.0],
  "seeds": "cs4examplemod:seeds",
  "crops": "minecraft:carrot"
}
```

* __maxAge__: The maximum number of stages this block has. A maxAge of 0 means the block will only have one stage. The maximum value for this attribute is 15. Default value is 7.
* __growthFactor__: This specifies how fast the crop will grow. A value of 1.0 is as fast as regular crops, 2.0 is twice as fast, 0.5 is half as fast. This value has to be greater than 0.0. Default value is 1.0.
* __heights__: This specifies the heights for each stage of the crop. If omitted, the height of the crop will linearly increase to 1.0 depending on the maxAge. For example if the maxAge is 3 the calculated heights will be `[0.25, 0.5, 0.75, 1.0]`.
* __seeds__: This is a BlockDrop defining the seeds that this block will drop. If the block is harvested at its maximum age it will drop multiple seeds just like regular crops.
* __crops__: This is a BlockDrop defining the crops that will drop if the block is harvested at its maximum age.

Block state properties: age. It has values between 0 and the value of maxAge, including both.

# Fence Gate
Type name: __block:fenceGate__

This is a fence gate block. It does not support metadata subtypes. It has the following addition attributes:

```json
{
  "opensWithRedstone": true,
  "openWithHands": true
}
```

* __opensWithRedstone__: Specifies whether the fence gate can be opened or closed using redstone. Default value is true.
* __opensWithHands__: Specifies whether the fence gate can be opened or closed using hands (right-clicking). Default value is true.

Block state properties: facing (north, south, east, west), in_wall (true, false), open (true, false).

# Wall
Type name: __block:wall__

This is a wall block. It supports all 16 metadata subtypes. It has no additional attributes.

Block state properties: subtype (0 to 15), north (true, false), south (true, false), east (true, false), west (true, false), up (true, false)

# Trap Door
Type name: __block:trapDoor__

This is a trap door block. It does not support metadata subtypes. It has the following addition attributes:

```json
{
  "opensWithRedstone": true,
  "openWithHands": true
}
```

* __opensWithRedstone__: Specifies whether the trap door can be opened or closed using redstone. Default value is true.
* __opensWithHands__: Specifies whether the trap door can be opened or closed using hands (right-clicking). Default value is true.

Block state properties: facing (north, south, east, west), half (top, bottom), open (true, false)

# Torch
Type name: __block:torch__

This is a torch block. It does not support metadata subtypes. It has the following addition attributes:

```json
{
  "spawnParticles": true
}
```

* __spawnParticles__: Specifies whether the torch should spawn flame and smoke particles. Default value is true.

Block state properties: facing (up, north, south, east, west)

# Button
Type name: __block:button__

This is a button block. It does not support metadata subtypes. It has the following addition attributes:

```json
{
  "pressedTicks": 20,
  "triggeredByArrows": false
}
```

Block state properties: facing (up, north, south, east, west), powered (true, false)

* __pressedTicks__: The number of ticks that the button remains in the pressed state. Default value is 20.
* __triggeredByArrows__: Specifies whether the button can be pressed by arrows. Default value is false.

# Pane
Type name: __block:pane__

This is a pane block (glass pane, iron bars, etc.). It supports all 16 metadata subtypes. It has no additional attributes.

Block state properties: subtype (0 to 15), north (true, false), south (true, false), east (true, false), west (true, false)

# Pressure Plate
Type name: __block:pressurePlate__

This is a pressure plate block. It does not support metadata subtypes. It has the following additional attributes.

```json
{
  "pressedTicks": 20,
  "selector": "everything",
  "onSound": "block.wood_pressureplate.click_on",
  "offSound": "block.wood_pressureplate.click_off"
}
```

* __pressedTicks__: The number of ticks that the pressure plate remains in the pressed state. Default value is 20.
* __selector__: This defines what entities can trigger the pressure plate. This is either the name of the entity (minecraft:sheep, minecraft:creeper) or one of the these: everything, nothing, livings, players, items. Default value is everything.
* __onSound__, __offSound__: The name of the sound when the pressure plate is pressed or unpressed. Default values are block.wood_pressureplate.click_on and block.wood_pressureplate.click_off

Block state properties: powered (true, false)