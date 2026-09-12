Use instructions for G_mule

-This meta requires:
	-Mag-Tools
	-Mag-Filter
	-Utility Belt

-Recommend also using:
	-Oracle of Dereth
	-Virindi Global Inventory

-Utility Belt networking enabled on each character:
	-Go into Utility Belt -> Settings -> Networking
-Click on “Tags” and assign the following network tag for each mule:
	-Armor mule = armor_mule, three
	-Clothing mule = clothing_mule, three
	-Jewelry mule = jewelry_mule, three
	-Rare mule = rare_mule, three
	-Salvage mule = salvage_mule, three
	-Weapon mule = weapon_mule, three
-Take this opportunity to enable “Track All Items” in Virindi Global Inventory. Let all the items scan before logging off, and also confirm /ub opt set VTank.PatchExpressionEngine true is enabled.

-All autopack and item giver .utl profiles must be placed into the correct folders (see example files):
-Item giver profiles go into “Documents\Decal Plugins\UtilityBelt\itemgiver”
-Autopack profiles go into “Documents\Decal Plugins\Mag-Tools” and must be appended with .autopack (ex. Garmor.autopack)

-All 3 of your accounts must be logged in. Your main character, your primary mule, and preferably your armor mule. 
-All characters should be within 20m in the same room. The meta will autotarget and follow to ensure mules are within range before giving items, but this will not work if they are in completely different rooms and get stuck on walls.

-The only thing you need to customize in the meta file is the names of your main character and mules. The reason this is distributed as an .AF is because it expects you to go in and modify the names before attempting to use the meta. 

-Once everything is set up, /tell your primary mule “mule” to start the meta. Customize the various loot and autopack profiles to suit your needs. You can also /tell “reset” to stop the sequence, log in your armor mule and go back to the default state.

-This meta does not handle your main character recalling to the marketplace and dumping all your loot on the primary mule. There are many different methods which already accomplish that. This is strictly for item transfer from the primary mule to secondary mules, and automatic bag organization.

-There is no autopack file for rares yet, but it still autopacks

MagTools Auto startup instructions:

-Add the following MagTools start-up commands to your primary mule (Tools -> Character -> On Login Complete):
	/vt meta load G_mule
	/vt start
