InterModComms(IMC)技术用于给其他的模组发送信息. 这可以用于——举个例子, 启用其他mod中的一项特色功能.

Type name: __imc__

```json
{
  "type" : "string",
  "modId": "customstuff4",
  "key": "test",
  "value" : "example value"
}
```
	
* __type__: 
  * 该属性用于决定 `value` 的类型. 该属性值可以是下面中的一个:
  * * `string`(字符串)
  * * `nbt`(NBT)
  * * `resource`(资源)
  * * `itemstack`(物品实例)
  * * `function`(函数?)
  * `resource` (资源)是一个 `ResourceLocation`(内部资源项)
  * `function` 使用字符串作为值, 但对其的处理方式不同. 你发送的内容是由接收的mod所决定的.
* __modId__: 接收信息的mod
* __key__: 信息的键
* __value__: 信息的值