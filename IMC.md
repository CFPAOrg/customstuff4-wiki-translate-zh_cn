InterModComms (IMC) are used to send messages to other mods. This can be used, for example, to access a feature of another mod.

Type name: __imc__

```json
{
  "type" : "string",
  "modId": "customstuff4",
  "key": "test",
  "value" : "example value"
}
```
	
* __type__: This defines the type of the value. This is one of string, nbt, resource, itemstack or function. resource is a ResourceLocation, function uses a string for the value but is handled differently. What you have to use is defined by the mod that the message is being sent to.
* __modId__: The id of the mod that the message is being sent to.
* __key__: The key of the message.
* __value__: The value of the message.