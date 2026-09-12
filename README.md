# G_Mule

A lightweight mule-management meta for managing item transfer from a primary mule to secondary mules, with automatic bag organization and autopack support.

## Requirements

This meta requires:

- Mag-Tools
- Mag-Filter
- Utility Belt

Recommended additional tools:

- Oracle of Dereth
- Virindi Global Inventory

## Utility Belt networking setup

Enable Utility Belt networking on each character:

1. Open Utility Belt
2. Go to `Settings -> Networking`
3. Click `Tags`
4. Assign the following network tag for each mule:

- Armor mule = `armor_mule, three`
- Clothing mule = `clothing_mule, three`
- Jewelry mule = `jewelry_mule, three`
- Rare mule = `rare_mule, three`
- Salvage mule = `salvage_mule, three`
- Weapon mule = `weapon_mule, three`

Also make sure to enable `Track All Items` in Virindi Global Inventory, let all items scan before logging off, and confirm that `/ub opt set VTank.PatchExpressionEngine true` is enabled.

## Files and folders

All autopack and item giver `.utl` profiles must be placed in the correct folders:

- Item giver profiles go into `Documents\Decal Plugins\UtilityBelt\itemgiver`
- Autopack profiles go into `Documents\Decal Plugins\Mag-Tools` and must be named with the `.autopack` extension, for example `Garmor.autopack`

## Setup notes

- All 3 of your accounts should be logged in: your main character, your primary mule, and preferably your armor mule.
- All characters should be within 20 meters in the same room.
- The meta will auto-target and follow to keep the mules in range before transferring items, but this will not work if the characters are in completely different rooms and get stuck on walls.
- The only thing you should customize in the meta file is the names of your main character and mules.
- This file is distributed as an `.AF` because it expects you to modify the names before using it.

## How to use

Once everything is set up:

1. Tell your primary mule `mule` to start the meta.
2. Customize the loot and autopack profiles as needed.
3. Use `reset` to stop the sequence, log in your armor mule, and return to the default state.

## Important limitations

- This meta does not handle your main character recalling to the marketplace and dumping all loot onto the primary mule.
- This is strictly for item transfer from the primary mule to secondary mules and automatic bag organization.
- There is no autopack file for rares yet, but the meta still autopacks them.

## MagTools auto-startup commands

Add the following MagTools startup commands to your primary mule under `Tools -> Character -> On Login Complete`:

```text
/vt meta load G_mule
/vt start
```
