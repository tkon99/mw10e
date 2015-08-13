# mw10e - Info
I came up with the idea to write this documentation because I wasn't able to find it elsewhere.
This documentation has the following structure:
- Definition of *mw10e*
- Locations of the *application* and it's *game files*
- Information about the *application*
- Information about the *game files*

## Definition of *mw10e*
*"Minecraft: Windows 10 Edition is an adaptation of Minecraft Pocket Edition to run on the universal Windows 10 platform. It contains the same features as in Pocket Edition with a few additions, and is also capable of running on devices such as the HoloLens.*

*It was announced on July 4, 2015, and a beta version was released on July 29, 2015 for £7.69, $9.99, or €9.89 on the Windows Store. People who have purchased the PC edition of Minecraft can get the Windows 10 edition for free."*

**(source: [http://minecraft.gamepedia.com/Windows_10_Edition](http://minecraft.gamepedia.com/Windows_10_Edition))**

## Locations of the *application* and it's *game files*
In mw10e the files once found under %appdata% (for the Java/old game) are now split into two separate folders in two totally different locations. The first part is where the game itself resides. See: The application. The second part is where the game's stored user data goes, such as worlds, settings, etc. See: Game files

#### The application
Because mw10e is a metro/modern application it doesn't use the ordinary "Program Files" folder. It uses a much more protected folder inside the "Program Files" called "WindowsApps" instead. This is where all the game's static files are stored (the ones that don't change while playing, such as logos, assets and the game's code).

To gain control over the folder (which is disabled by default) you need to give your user account permission manually. [This youtube video](https://www.youtube.com/watch?v=HSrkYvVjEnY) explains it for you. (It's a little outdated (Windows 8) but the process for Windows 10 is exactly the same)

Once you've gained access to the folder you can view and edit the files the game uses. They are located in a folder named: *Microsoft.MinecraftUWP_xxxxxxxxxx* (x's are numbers or letters and UWP stands for *Universal Windows Platform*). More on the use of these files later.

#### Game files
The Game files are easier to access than the application files. They contain everything from settings to game saves.
To get to the Game files first go to your account's folder (**C:\Users\** and click your name), then make sure hidden items are visible (click "View" on the top of the window and check "Hidden Items"). Once you've done that navigate to "AppData" then enter the "Local" folder, continue to the folder named "Packages" and locate the folder *Microsoft.MinecraftUWP_xxxxxxxxx*. Here you can look around and find various files. More on the contents later.

## Information about the application
Inside the folder you gained access before we can distinguish several types of files:
- Images/Sprites (.png/.jpg)
- Config files (.json/.xml)
- Binary/other

Using this knowledge we can practically alter every aspect of the game (modding). To get started I suggest you take a look at the "data" folder. You'll find that all config files in the sub folders are in json format (which is today's standard and very readable). If you look inside the "ui" folder you'll even find that you can basically customize every single aspect of the game's UI through these json files. (I'll update this after I've sudied their exact syntax and purpose)

As far as sprites ("data/images") are concerned you can basically alter the game's appearance/experience using these, in the future this will allow for custom "texture/resource" packs. (As sound is included too. Perhaps I'll make a tool real quick to do that... If you want to stay tuned follow me on github)

(Binary/other info will follow soon)

## Information about the game files
Inside the game files folder you'll find many folders (some even empty) but you'll want to focus on the "LocalState" folder since that's where all the cool stuff is at. If you've imported a skin the file will be copied to this folder (with the exact same filename). If you haven't done that already you'll find only one folder called "games" enter it and continue to "com.mojang".

Now you'll find two folders, go ahead and open "minecraftWorlds". You'll find yourself some folders (that is if you've created a world/worlds). The name of the folder is actually the *base 32 encoded* number of the world. If you'd decode them you'll get 0 for "DboDAHIrAgA=", etc.

Inside any of these you'll find yourself a folder structure starting at the root with the level.dat files (we know from previous minecraft games. Needs further research), a folder called db (which I haven't had time for to take a look at) and a text file called levelname.txt (contains the name of the level as it appears in the game in plain text).

Now we go back to the two folders we started out with (where we entered "minecraftWorlds") and we now enter "minecraftpe". This folder seems to contain the game's settings and a serverlist which are easily readable and changeable.

* * *

##### Note: this isn't finished yet and may contain mistakes/wrong info eventhough I've done my best to limit it. Also this info will be updated frequently as we learn more about the game's files.

***Microsoft, Minecraft, Minecraft Pocket Edition and Minecraft Windows 10 Edition all belong to their rightful owners. I'm not affiliated with them in any way.***