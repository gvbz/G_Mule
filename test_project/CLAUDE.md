# Agent Instructions
* We are going to be creating meta files for the game Asheron's Call, these files automate a variety of gameplay tasks like combat, navigation, npc interaction, item transfer and salvaging. The game uses a program called Decal, which is a specialized third-party software framework that allows developers to create plugins for Asheron's Call. It acts as an interface layer between the game client and custom plugins, enabling features like advanced loot filtering, mapping, automation (metas), and enhanced UI displays. Within Decal, there is a suite of plugins called Virindi Tools, specifically Virindi Tank. Virindi Tank uses .met and .nav files to execute the automation tasks within the game. We will be using an editor called metaf, which is a powerful meta/nav editor in an alternate format to that used by the Virindi Tank plugin. metaf provides full-featured capabilities for editing and straightforward bidirectional translation between .met/.nav and .af file formats, with Virindi Tank running the end results. Visual Code Studio will be using the metaf extension, which is an extension designed to enhance your experience when working with the metaf scripting language, widely used for wirting Virindi Tank metas. Whether you're a seasoned developer or new to programming, this extension aims to provide a seamless environment for coding and scripting.
* Using the Run on Save extension for Visual Studio Code, we will be able to run a configured metaf shell command when a file is saved in vscode, to automatically output a .met file, which can be used by Virindi Tank. The following code should be added to all .af files we create.
    "runOnSave.commands": [
      {
        // Match af files except names start with `_`.
        "globMatch": "**/[^_]*.af",
        // Change this to your metaf bat file path
        "command": "C:\\metaf\\_OverwriteDest.bat \"${file}\"",
        "runIn": "terminal"
    },
  ]
* I will provide as much documentation as possible for you to research in order to develop a thorough understanding of the meta creation workflow and code, along with several working examples of .af files.
* I have provided metaf readme documentation that you must research and understand. Keep in mind that this is older documentation with references to Notepad++, and we are now using Visual Studio Code as the IDE, but all the same rules and color coding apply. The file is located in the "ref" folder of the project direction and is called "metafREADME.af"
* I have also provided the metaf visual coding documentation that you must research and understand. The file is located in the "ref" folder of the project direction and is called "metafReference.af"
* You must conduct very thorough and as much research as possible from the resources provided. It's important to understand all Expressions, Chat command messages, and interactions between different plugins.
* Always provide detailed code documentation and commenting so I can also develop an understanding of the program and assist with troubleshooting.
* It's important to know that when you are creating code references to navigation routes that are located at the end of the code base, I will provide you with the detailed navigation coordinates that will go there. It is not possible for you to automatically create these, because they come from in-game topography data.
* UtilityBelt is another plugin that provides additional functionality and can work in conjunction to Virindi Tank, we can leverage UtilityBelt chat commands and expressions to further customize our metas. Get familiar with all UtilityBelt documentation, including chat command line and expressions.

## Example File Explanations
The following examples are located in the "examples" folder of the project directory, here is brief overview of what they do:
* "Meta_Society.af" is a meta that will automatically run a series of quests after the player gives the fellowship chat command "!start".
* "LegendaryQuests.af" will automatically detect and list which legendary quests the player has completed. 
* "RecallExamples.af" gives examples of meta states that automatically recall to a particular location based on spell identifier and detected land block.
* "TusksAndPincers.af" is an excellent example of a functioning meta that will automatically run a series of combat related tusk and pincer collection quests. It will run a quest, automatically recall you outout of the dungeon, then run another quest. At the end of the series of quests, it will turn in all of the collection items to their applicable vendors and then place useless items like gems and heal kits in the trash. 
* "auto_hunt_v1.af" is the .af conversion of the first .met file I created using the in-game editor. What it does is in the Default state, it automatically patrols and hunts a particular area, collecting loot until the characters burden is greater than 89%. When that happens, the character will automatically recall back to the marketplace, navigate to a second character that i have logged in, and transfer all full bags of salvage, then return to the original Default state, recall and continue hunting. To transfer items to the Gmule character, a specific loot profile is used to define the bags of salvage transferred.
* "directcontrol2share.af" is meta program that controls multiple characters using UtilityBelt command lines and custom Virindi View windows. Make note that I would like to implement Virindi View gui windows wherever possible. Documentation can be found here: "auto_hunt_v1.af"
* "RynBuyLumKits.af" is a meta program that automatically purchases luminance kits for your character and also uses custom view windows.
* "MetaQ.af" is a complex meta that controls multiple players and automatically does a series of quests the user has defined. There are important concepts in here to understand like how to switch between different meta files.

## Background References
Pull background information from the following websites:

This is the main virindi tools website which explains their suite of plugins:
http://www.virindi.net/wiki/index.php/Main_Page

This is Virindi Tank specific documentation:
http://www.virindi.net/wiki/index.php/Virindi_Tank
http://www.virindi.net/wiki/index.php/Virindi_Tank_Meta_System

These are important meta expressions and chat message capture conditions:
http://www.virindi.net/wiki/index.php/Meta_Expressions
http://www.virindi.net/wiki/index.php/Meta_ChatMessageCapture_Condition

This is the documentation for the UtilityBelt plugin:
https://utilitybelt.gitlab.io/docs/overview/
https://utilitybelt.gitlab.io/docs/command-line/
https://utilitybelt.gitlab.io/docs/expressions/

This explains meta views:
http://www.virindi.net/wiki/index.php/Meta_Views

This is the github for metaf:
https://github.com/JJEII/metaf

This is the gitlab for the metaf extension:
https://gitlab.com/metaf/metaf-vscode-extension

General information on the game Asherons call:
https://asheron.fandom.com/wiki/Home

Installation directory of asherons call:
C:\Turbine\Asheron's Call

Installation directory of Virindi tank:
C:\Games\VirindiPlugins

Installation directory of UtilityBelt:
C:\Users\gabos\Documents\Decal Plugins\UtilityBelt

Decal Plugins folder:
C:\Users\gabos\Documents\Decal Plugins


## The Feedback Improvement Loop
* I will be manually testing the files for functionality because there is no way to run or test the code within an IDE. The files we are creating run on a live online game client. The file will either work as intented or encounter a bug, in which case I will provide direct analysis and feedback to try and resolve the error. 