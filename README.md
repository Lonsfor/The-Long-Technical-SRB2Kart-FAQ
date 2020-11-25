# The Long Technical SRB2Kart FAQ
By JugadorXEI, also made possible with the help of tons of community members. Like you!
Before we start, check out [hyuu.cc](hyuu.cc)’s FAQ, which likely covers 80% of your questions (such as how to host netgames, and addon-related stuff). This covers what is not covered (mostly).


## I have a problem with a custom build! (And/or) A custom character! (And/or) A custom race track/level! (And/or) A Lua addon! (Or maybe it’s not a problem, but you wish to leave feedback)
* Custom build support goes to #hardcode in the Kart Krew Discord, or to its respective thread on the Message Board.
* Custom characters having issues go to #custom-racers in the KK Discord, or to its respective thread on the Message Board. If you need help doing sprites, #spriting-help in the KK Discord is there to help, if possible.
* Custom levels having problems go to #custom-courses in the KK Discord, or to its respective thread on the Message Board. If you’re having trouble doing something in Zone Builder yourself, you can get support on the #course-help channel in the KK Discord.
* And finally, custom LUA addons having problems go to #graphics-lua-misc in the KK Discord, or to its respective thread on the Message Board.

Remember that, when you leave feedback, or you are reporting a problem, be as constructive as possible. If you’re found a bug in a Lua addon, reproduction steps (AKA, how to cause a problem consistently) help a ton!

Keep in mind that people who provide addons, do so for free, and out of passion and love for the game. Support is not guaranteed. However, please do not get angry when issues don’t get fixed immediately, as authors do have other stuff to do than to keep their addons 100% bug-free. 

And finally, don’t inquire about these problems on the #tech-support channel in the Kart Krew Discord, which is for base game bugs and problems!

## I am using the OpenGL renderer, but models are invisible! (Or) Certain models are visible, and some are completely invisible!
Make sure there is a “mdls” folder and a “mdls.dat” file in your SRB2Kart folder. If there isn’t, that might mean something went wrong in your SRB2Kart installation which might have made it exclude the model files.

If certain models are invisible/not being rendered, what this means is that the model is defined in the mdls.dat file, but the model does not actually exist, or there could be a parsing error in the file. To fix it, open the mdls.dat file with a text editor, and make sure each line follows this same pattern:
`FILE PATH/FILE.md3 3.0 0.0`

Where the first parameter is a name, the second is a (relative) path to a .md2 or .md3 file, and the third and fourth parameters are numbers with a decimal (usually referring to scales). The most common syntax errors are usually lack of spaces, or a dot between the last two numbers.
## I am using the OpenGL renderer, but it crashes my game!
It could be that:
* Your graphics card/GPU drivers are out of date. You need to research which GPU your computer is using, and download its most up-to-date drivers. Or,

* The game does not have permission to use mdls.dat/the mdls folder.
  * In Windows, this happens when you install the game in the Program Files folder - don’t! Please use any other folder that does not require administrator privileges!
  * In Linux, if you used the PPA to install the game, it will be in /usr/games/SRB2Kart. If the SRB2Kart folder is owned by root, use chown to give yourself ownership of the folder. This should allow it to start.

## How do I check if my ports are open?

You can use [Jameds’s Port Checker](https://www.jameds.org/SRB2/port/). [Is My Port Open](https://ismyportopen.com/) also works.

## How do I check if my server is being advertised on the Master Server?

Check the [Master Server link](https://ms.kartkrew.org/ms/api/games/SRB2Kart/7/servers?v=2) and see if your IP is being advertised!

## I can’t connect to the master server!
The master server is either down, or you might not be using the correct master server link.
In the former case, just wait it out! In the latter case, check if the master server is “https://ms.kartkrew.org/ms/api”, either by opening the developer console (with the tilde button - the one above Tab) and writing “masterserver” and the address, or by going to Options > Server Options > Advanced Options > Server Browser Address.

## How do I backup my save file?
In the game folder,
* “kartdata.dat” contains your save file data, such as your Record Attack medals.
* “kartconfig.cfg” contains your game settings, such as controls or game resolution.
* “replay/kart” contains your Record Attack ghosts.

Back these up depending on your needs, such as playing between different computers!

## Discord Rich Presence does not work!
It might not be on. Go to Options > Data Options > Discord Options, and turn Rich Presence on if it was off. You can also turn rich presence on through the console, with `discordrp on`

From this point onwards, Discord is usually smart enough to know the game you’re playing. However, if this is not the case, check the following in Discord:
* Go to User Settings > Game Activity.
  * Make sure “Display currently running game as a status message” is turned on.
  * If your game is not automatically detected by Discord, press the blue “Add it!” button, and select “SRB2Kart”.


You may need to restart Discord through the CTRL+R shortcut or by simply reopening it.

The officially-distributed Linux and macOS versions of the game do not come with Discord Rich Presence support by default. It is, however, possible to compile the game yourself to add it in, by utilizing the [source code](https://github.com/STJr/Kart-Public), following the [makefile guide](https://wiki.srb2.org/wiki/Source_code_compiling/Makefiles), getting the [Discord RPC libraries and dynamic library](https://github.com/discord/discord-rpc/releases), enabling the `HAVE_DISCORDRPC=1` flag and then compiling. also check out https://kart.moe/building-srb2-kart-for-linux/

## How do I open SRB2Kart in OGL/Software mode through Steam?
In 1.3, the game remembers your renderer choice as long as you boot it using their respective .bat (batch) files or use their respective startup parameters at least once.

However, if you want your Steam shortcut to force a particular renderer choice, you must use the **-software** and/or **-opengl** startup parameters. In order to do this:
* Add the game on Steam - go to the library tab, and on the lower left corner of the screen, click “Add a game” then “Add a non-Steam game”.

* On the dialog that appears, click “Browse”, and a new dialog will appear. Go to the folder where the game is, click on its executable, then press Open.

* The game will now appear on the former dialog and now checkmarked. Click on “Add Selected Programs” to proceed.

* The game should now appear in your library. Right-click the game, then press Properties. On the Property window that appears, press “Set Launch Options”.

* In the Launch Options dialog, you should be able to set the startup parameters you need. Put `-opengl` if you wish the game to start with the OpenGL renderer, or `-software` to use the Software renderer. Click “Ok”, and now it should work the way you want it to!

## My screen gets cut off when using a big resolution!
In Windows 10,
* Right Click the srb2kart.exe executable, then click Properties.
* The Properties dialog should appear - go to the Compatibility tab and then press the “Change high DPI settings” button.
* A new window will appear that will say “Choose the high DPI settings for this program”. In the High DPI scaling override section, check the “Override high DPI scaling behaviour” selection, and then on the dropdown menu, let the “Application” handle it. Press Ok on this window, then Ok/Apply on the properties window. The black bars should disappear.

## SmartScreen/My anti-virus says the SRB2Kart installer/patcher is not trusted and I can’t open it!
If SmartScreen prevents you from running the installer or patcher, on its dialog window, click “More info”. The “Run anyway” button will appear afterwards, from which you can click to proceed with the install.

If your antivirus is blocking the installer, let your antivirus make an exception for it specifically.

Do not worry about the installer being unsafe - as long as you download it from the [Message Board](https://mb.srb2.org/showthread.php?t=43708) or [GitHub releases](https://github.com/STJr/Kart-Public/releases/), you should be getting a safe download.


## Is there a list of commands, variables and start-up parameters for Kart?
Console commands and variables can be found [here](https://wiki.srb2.org/wiki/Console/Commands) and [here](https://wiki.srb2.org/wiki/Console/Variables). Kart-specific variables and commands can be found [here](https://wiki.srb2.org/wiki/User:ThatAwesomeGuy173/SRB2Kart/Variables). Start-up parameters can be found [here](https://wiki.srb2.org/wiki/Command_line_parameters).

## My game runs out of memory often!
There are two things you can do:
* If you’re using a 32-bit build of the game, you can use [NTCore’s 4GB Patch](https://ntcore.com/?page_id=371) to allow 32-bit builds of the game to have large memory awareness, or
* If you’re savvy, you can build a 64-bit version of the game. 64-bit builds of the game are not officially supported, but it will allow you to use large amounts of memory and virtually not run out of it so long as you have enough. You can learn how to compile the game [here](https://wiki.srb2.org/wiki/Source_code_compiling) or [here](https://wiki.srb2.org/wiki/User:Jamesr/Makefile).
