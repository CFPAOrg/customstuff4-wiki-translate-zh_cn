# 矿脉
该生成器可用于类似矿脉的生成, 如铁矿石或粘土.

类名: __worldGen:ore__

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

* __block__: 该属性指定了一个ResourceLocation, 用于调用生成的方块.

* __meta__: 该属性定义了生成的方块的元数据. 默认为 `0`.

* __target__: 该属性指定了一种自然生成方块作为生成源, 矿脉将生成在该生成结构内. 默认值为 `minecraft:stone`.

* __targetMeta__: `target` 的方块实例的元数据. 默认为 `0`.

* __count__: 该属性定义了每个区块会尝试生成该矿脉的数量的多少. 默认为 `1`.

* __size__: 该属性定义了在每个生成实例里生成的 `block` 的多少. 默认为 `10`. 注意, 实际情况可能会与这个属性值有所出入.

* __minHeight__: 该矿脉的最小生成层数. 默认为 `0`.

* __maxHeight__: 该矿脉的最大生成层数. 默认为 `64`.

* __dimension__: 该矿脉会在哪个世界生成, 默认为 `0`(overworld, 即主世界)

* __weight__: 该值越大, 生成器在世界生成的过程中运行的越晚, 这意味着其他生成器在此之前运行.(译者注: 该值是表示生成的占比, 占比越大, 生成的越多)