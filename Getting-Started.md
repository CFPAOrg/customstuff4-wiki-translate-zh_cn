To get started, you need to create a new folder in the mods directory of you minecraft installation. In that folder create a file called _cs4mod.json_ with the following content:

	{  
	  "id": "mymod",
	  "name": "My Mod",
	  "version": "1.0.0"
	}

Replace _mymod_ with the id for your mod. The id must only contain lowercase letters (a-z), numbers (0-9) and underscores.  
Replace _My Mod_ with the name for your mod.  
Replace _1.0.0_ with the version of your mod.

You can now start Minecraft, which will create the necessary files for your mod to work. Note that your mod will only appear in the mod list after the second start of Minecraft. There should now be a folder called _cs4mod_ next to _cs4mod.json_.  
That's it. You've set everything up.

To change the version of your mod, edit the _cs4mod.json_ file, delete the _cs4mod_ folder and start Minecraft. Make sure to not load a world before the second start of Minecraft as your mod will not be loaded until then.