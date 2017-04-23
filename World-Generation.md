# Ore
This generator can be used for ore-like generation, like iron ore or clay.

Type name: __worldGen:ore__

```json
{
	"block" : "minecraft:wool",
	"meta" : 1,
	"target" : "minecraft:stone",
	"targetMeta" : 1,
	"count" : 1,
	"size" : 10,
	"minHeight" : 0,
	"maxHeight" : 64,
	"dimension" : 0,
	"weight" : 1
}
```

* __block__: This is a ResourceLocation specifying that block that is being generated.

* __meta__: This defines the metadata of the generated block.

* __target__: This is a ResourceLocation specifying what block is being replaced to generate the block. If omitted, stone is being replaced.

* __targetMeta__: This defines the metadata of the target block. Omit, to replace all metadata values.

* __count__: This defines the number of generations per chunk. Defaults to 1.

* __size__: The number of blocks in each generation. Defaults to 10.

* __minHeight__: The minimum height that the block is generated in. Defaults to 0.

* __maxHeight__: The maximum height that the block is generated in. Defaults to 64.

* __dimension__: The dimension id in which that block is being generated. Defaults to 0 (overworld).

* __weight__: The bigger this value, the later the generator runs in the world generation process, which means other generators run before this one.