# ATBCrafter
The Automatic TextBox Crafter (ATBCrafter) is a Java FFXIV crafting utility that does not access the game's memory / process in any way and that can branch crafting actions based on quality.

The application is available for 2.99€ through PayPal. Download links are made available via email by FetchApp after payment.

<a href="http://atbcrafter.fetchapp.com/sell/dc75daf1"><img src="http://www.paypal.com/en_US/i/btn/btn_buynow_LG.gif" alt="" /></a>

If you have already bought the application or obtained the application from someone else and want to contribute further for its development, you can always donate. Any amount of money helps and is appreciated.

<a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=3PTK9AH56YGPE"><img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" alt="" /></a>

The current version is version 1.15, released in 2020/08/24. Support for patch 5.3 has been added with this release.

## Shadowbrigers UI Changes Notice
Due to the changes to the crafting UI in patch 5.0 for Shadowbringers, the application may have to be reconfigured for some features to work again. However, given that the quality status text indicator (poor/normal/good/excellent) will have a different color, it is unknown whether the current algorithm that detects it will work.

If a new detection method is required, a new version of the program will be released soon after 5.0, alongside the support for autotranslating the new actions.

## Table of Contents
 - [Requirements](#requirements)
 - [Features](#features)
 - [Cons](#cons)
 - [Screenshots](#screenshots)
 - [Configuration Process](#configuration-process)
   - [New Version Configuration](#configuration-of-the-latest-version-106---20180827)
 - [Available Macro Commands](#available-macro-commands)
 - [Macro Example](#macro-example)
 - [Purchase and Updates](#purchase-and-updates)

## Requirements
This is a Java application that supports the PC version of FFXIV _only_.

The application should work on any PC (tested with Windows, should work on Mac and Linux for the most part but it is untested) that has Java SE installed. Java can be downloaded from the Oracle's website linked below. 

<a href="http://www.java.com"><img src="http://download.oracle.com/technetwork/java/get-java/getjavasoftware-120x30.png" alt="Get Java Software" border="0" width="120" height="30" /></a>

If you have any issues with the application not being able to save configuration settings, please make move the application to a location such as within your "Documents" folder or the Desktop.

## Features
- **Does not access the game's memory in any way.**
  - Only simulates key / mouse button presses and takes screenshots.
  - Does not break on new patches, nor does it require any kind of memory pointers to work!
- **Simple to use!**
  - You can just copy-paste your macros after configuring a few simple things and it should work. However, many advanced features allows you to craft multiple items without having to start each craft manually and to avoid poor qualities on your "Byregot's Blessing"!
- **Detects quality during the crafting process.**
  - This allows for macros to use different actions based on quality, such as switching actions around to prevent a poor quality on the "Byregot's Blessing / Brow / Miracle".
  - Matching can also be done by similarity between images if the exact matching fails for some reason.
- **Conditional Macro Execution**
  - Additionally to being able to use different actions depending on the current crafting condition quality, it is now possible to also use different actions based on the current amount of spare CP (to add a possible Innovation, for example), the number of failed Flawless Synthesis actions (for "Maker's Mark" rotations) current amount of Inner Quiet stacks (to use "Reclaim" perhaps, could be more useful in the future).
- **Automatically detects when the next action is ready to be used.**
  - Makes crafting faster when compared to using in-game macros.
  - Prevents lag spikes from messing up the craft.
- **Can craft the same item many times without human intervention.**
  - The number of times that a macro is to be executed can be defined.
  - The location of the "Begin Synthesis" button can be defined, which once detected is pressed for the next craft.
- **Actions can be tagged to have "Tricks of the Trade" used before them if the quality is good or excellent.**
  - The number of "Tricks of the Trade" used can be limited, so it can be possible to optimize a "Maker's Mark" rotation.
- **"Hasty Touches" are upgraded to "Basic / Precise Touches" based on context.**
  - The amount of spare CP that can be used to perform "Basic / Precise Touches" instead of "Hasty Touches" can be defined in a macro.
  - Tries to upgrade "Hasty Touches" that land on good / excellent qualities, so more "Precise Touches" can be used if the action is available for the best HQ chance possible.
  - The CP obtained through "Tricks of the Trade" is automatically used to upgrade "Hasty Touches".
- **Automatic Action Localization**
  - If the FFXIV client is set to a language other than English, it is possible to have the program automatically translate the actions in the macro to a specific language.
  - Remember to set the correct localization to avoid issues with "Hasty Touch" upgrades and "Tricks of the Trade" executions.
- **Can pause, stop immediately and stop executing after the current craft.**
  - Pauses the execution when the application is focused, allowing to stop the current craft more easily.
  - When using Microsoft Windows, execution can be paused if FFXIV is not the focused application.
- **Create, Load, Edit and Save crafting macros on the application.**
  - Macros files can be loaded directly by dragging them into the macro text area.
- **Can be configured to perform trial synthesis easily.**
- **Undo and redo edits in the macring area using crtl-Z and ctrl-Y.**
- **Highlights the action queued to be executed during crafting.**

## Cons
Since the application does not access the game's memory to obtain data about the craft, the application **requires the game to be focused** to work.
It uses the game's textbox to perform actions, mouse button presses to begin crafts and takes screenshots to detect a craft's quality. Because of this, **this application only supports the PC version of FFXIV**.

Additionally, it also requires some configuration before it can be used. Fortunately, the configuration process only needs to be done once if the crafting log / crafting progress windows are not moved after the fact.

## Screenshots

### Main screen
The main screen shown below is divided into several sections: the menu bar, the loop controls and the macro editing and display area. 

<img src=main.png />

The area number 5 shows the control where the number of crafts to execute using the macro shown on area 7. While executing, each time the macro is completed this number is decremented, so it can be used to see how many crafts are left to complete the batch. The progress bar on area number 6 displays visually the batch progress. Once full, the batch execution is finished. 

The menu bar contains four different menus:

1. The macro menu, where macros can be opened and saved. It is also possible to close the application from here.

<img src=macro.png />

2. The execute menu, where the execution of the current opened macro can be started and stopped. The option to start a trial synthesis has also been added.

<img src=execute.png />

3. The options menu, where the application can be configured and several settings set, such as whether the "Precise Touch" can be used for "Hasty Touch" upgrades, if the application should be always on top and so on. It is also possible to open a small display window that displays the current mouse position.

<img src=options.png />

The configuration screen also shows the current mouse position at the bottom for convenience, the current setting for the location of the begin synthesis button, the location of an action that can be always used (such as "Basic Synthesis") to check when it is possible to use an action and the location of the top left and bottom right corners of the box area that encloses the crafting quality condition. These values can be obtained using the current mouse position at the bottom.

The quality condition box is used to capture and compare the quality condition with the pictures shown below these settings. If no picture is shown then the application still needs to be configured for that.

<img src=configuration.png />

4. The help menu, which can display a window with the available macro commands and a window with the current application version. 

<img src=help.png />

## Configuration Process
The configuration process is fairly straightforward. The image below shows the configuration window, accessed via the menu Options -> Configuration.

<img src=config_1.png />

First, set the application to be always on top and then open the crafting log in FFXIV. To configure the "Begin Synthesis button position", place your mouse over the Synthesize button ingame. Then, check the current mouse position in the application as shown. Take note of that position and copy the values into the respective fields.

Next, the "Action ready position" is configured in a very similar manner, as shown below.

<img src=config_2.png />

Locate an action in your hotbar that is always available to be used regardless of context (e.g. quality condition, current CP, etc.) such as "Basic Synthesis" or "Hasty Touch". Place your mouse over the action and take note of the mouse position on the application. Copy the values into the respective fields. **Note that with the recent changes to crafting "Careful Synthesis" is no longer a valid option for this purpose as it costs CP.**

Finally, the "Synthesis quality text area" needs to be configured. Since this requires an area of the screen, two positions are needed (the upper left corner and the lower right corner of the area). The image below illustrates the two positions needed.

<img src=config_3.png />

First, place your mouse somewhere around the upper left corner of the area where the quality condition text appears (doesn't have to be precise, but **make sure that the mouse is within the crafting progress window and that the circle to the left of the quality condition text is NOT in the area**). Once again, take note of the mouse position as shown in the application and copy it to the first two fields as illustrated below.

<img src=config_4.png />

Then, place your mouse somewhere around the lower right corner of the area where the quality condition text appears (once again, it doesn't have to be precise, but **make sure that the mouse is within the crafting progress window and that the circle to the left of the quality condition text is NOT in the area**). Take note once more of the mouse position as shown in the application and copy it to the final two fields as illustrated below.

<img src=config_5.png />

This concludes the configuration of the mouse positions for starting crafts, checking when actions can be used and for extracting the quality condition while crafting. All that there is left to do is to save the quality condition images that will match the configured area, so the application known what quality condition each image corresponds to.

To do so, select from the menu bar Options -> Configure Quality Detection as illustrated below. A window will appear that warns you about several things, such as the application needing to be configured as just explained until now, that you know the "Observe" action and that you are ready to craft something ingame. **It is recommended that the craft used for this does not used expensive materials, as the craft is not meant to be completed**.

<img src=config_6.png />

Pressing "Yes" will replace your current macro with one that allows for the quality condition configuration to be executed, as shown below, so be sure you save it first.

Then all that is needed to do is to start the macro execution.

<img src=config_7.png />

At this point, the application will start the craft and spam the "Observe" action over and over. This will continue until all four different quality conditions are detected, so **you might have to stop and restart the execution of this macro a few times if the excellent condition decides to not show up**.

When all four quality conditions are detected, a new window will appear as illustrated below.

<img src=config_8.png />

All that is required to do now is to select the quality condition option that matches the image shown and press "OK". After this is done for all four quality conditions, the application will save the images and the configuration process is completed. You can now use the application.

**_Note that the configuration is saved, so you only have to do this process once. However, if you move the crafting log window, the action used for the "Action ready position" or the crafting progress window, you'll have to reconfigure the respective portion of the application. While the first two cases only requires you to set a different mouse position, moving the crafting progress window not only requires you to configure a new "Synthesis quality text area" corner positions, but also to reconfigure the quality condition images, as the area might be different and the application will fail to match the previous saved ones._**

However, the application has been updated to allow small movements in the crafting progress window (under 50 pixels) to be fixed automatically by the application. Just head to the Configuration window and use the new button "Validate Quality Detection Area".

### Configuration of the Latest Version (1.06 - 2018/08/27)
Version 1.06 added many new features to the program and a few more configuration settings to the ones displayed in the Configuration Process section.

In terms of features, the program now has an "Actions Localization" setting in the "Options" menu:

<img src=localizations.png />

Setting the language that the FFXIV client is on will ensure that the correct action names will be used. **However, not all actions in all localizations were tested.** If there is an issue with any actions, please open the config.json file in the program's folder, find the action and correct its spelling if necessary. You can also add new actions if necessary come the next expansion and I'm slow to update the program.

~~The "Use Byregot's Brow" option was also added, which enables the replacement of any "Byregot's Blessing" action by the "Byregot's Brow" action when the number of current Inner Quiet stacks is at 5 or lower. Keep in mind that the success rate of "Byregot's Brow" is only 70% on non-specialist craft jobs.~~ Feature removed with the removal of "Byregot's Brow" from the game.

The configuration window was also updated to include four new position/areas:
 - The position of the trial synthesis button.
 - The area where the materials for the craft are selected.
 - The area where the current crafting progress value is shown.
 - The area where the current crafting quality value is shown.
 
<img src=new_config.png />

The image above shows the new configuration settings. The trial synthesis button position cam now be configured similarly to the Begin Synthesis button, allowing the application to perform trial synthesis more easily.

The Progress Value Area and Quality Value Area are configured the using a box similarly to the Quality detection text area. You just have to configure the Progress Value Area (1) and Quality Value Area (2) with the boxes shown below:

<img src=new_values_config.png />

The Material Selection Area is configured by selecting two different button positions: the NQ material button for the first material slot and the HQ material button for the sixth material slot, as shown below:

<img src=mats_config.png />

New actions have also been added and can be found in the next section, the Available Macro Commands.

## Available Macro Commands
In this section the available macro commands will be shown. Please configure the application as detailed above prior to using any macro.

### Pausing execution for a set amount of time.
`Usage:` /wait \<time\>

`Example:` /wait 3000

Waits the specified amount of time in milliseconds before executing the next action.

### Mouse click a given position on the screen.
`Usage:` /click \<x\> \<y\>

`Example:` /click 400 600

Moves the mouse to the specified x and y coordinates on screen and performs a mouse click.

### Setting the amount of space CP for "Hasty Touch" upgrades.
`Usage:` /spareCP \<x\>

`Example:` /spareCP 28

Sets the amount of spare CP usable to upgrade "Hasty Touches" into "Basic / Precise Touches".

The amount of spare CP is set to 0 by default.

### Using items on a set timer.
`Usage:` /timedo \<M\> \<x\> \<y\> \<T\>

`Example:` /timedo 29 400 600 3000

Exits the crafting log every M minutes to click on the screen location (x,y), then waits T milliseconds and reopens the crafting log using the default keybind "N". Must be placed before the "/mats" and "/craft" commands. **Make sure you do not use the search craft feature ingame, as it currently does not save the selected craft when exiting and reentering the crafting log!**

### Using items on a set number of crafts.
`Usage:` /loopdo \<N\> \<x\> \<y\> \<T\>

`Example:` /loopdo 10 400 600 3000

Exits the crafting log every N crafts to click on the screen location (x,y), then waits T milliseconds and reopens the crafting log using the default keybind "N". Must be placed before the "/mats" and "/craft" commands. **Make sure you do not use the search craft feature ingame, as it currently does not save the selected craft when exiting and reentering the crafting log!**

### Setting the HQ materials per craft automatically.
`Usage:` /mats \<N\> \<M1\> \[\<M2\> \[\<M3\> \[\<M4\> \[\<M5\> \[\<M6\>\]\]\]\]\] 

`Example:` /mats 14 3 0 1

Exits the crafting log every N crafts to reset the materials back to all NQ and then clicks on the HQ button for each material the defined number of times (the first material is clicked M1 times, the second M2 times, etc). Any missing number is defaulted to 0. Must be placed before the "/craft" command. **Make sure you do not use the search craft feature ingame, as it currently does not save the selected craft when exiting and reentering the crafting log!**

### Performing an ingame action.
`Usage:` /ac \<action name\>

`Example:` /ac "Inner Quiet"

The specified action is copied and pasted into the FFXIV chatbox as a command to be executed.

The "Hasty Touch" action is replaced by a "Basic Touch" if crafting condition is good or excellent, or if the remaining number of "Hasty Touch" actions can all be upgraded with the amount of spare CP available. If the "Precise Touch" action is available, it is used instead if the condition is good or excellent.

`Additional option:` -trick\[:N\]

Executes "Tricks of the Trade" before if condition is good or excellent and adds 20 CP to the amount of spare CP.

If an N limit to the number of tricks is added (e.g. -trick:3), then the "Tricks of the Trade" action is not executed if there have been N previous executions.

### Begin a craft.
`Usage:` /craft

`Example:` /craft

Makes the application click on the Begin Synthesis or Trial Synthesis button as soon as it appears. The button should be visible when the application starts executing.

### Configuring the quality detection.
`Usage:` /qualityConfig

`Example:` /qualityConfig

Starts an infinite loop of '/ac "Observe"' command executions. Only needs to be executed until all four different crafting qualities occurr within the same synthesis, after which the user will be prompted to map each saved image to a crafting quality.

### Crafting quality action branching.
`Usage:` /ifquality (poor|normal|good|excellent|good+)

`Example:` /ifquality excellent

Checks if crafting quality matches the specified quality and any following commands are only executed if there is a quality match. The "good+" option matches both the good and excellent quality conditions.

Nested action branching commands are supported.

Requires a prior successful quality configuration.

### "Inner Quiet" stack count branching.
`Usage:` /ifiq \<N\>

`Example:` /ifiq 6

Checks if "Inner Quiet" is at N or more stacks and any following commands are only executed if true. Note that the application only detects a successful Inner Quiet stack increase when the quality of the craft increases for some actions (like Hasty Touch). If quality is already at maximum it will not work properly.

Nested action branching commands are supported.

### Amount of spare CP branching.
`Usage:` /ifspareCP \<N\>

`Example:` /ifspareCP 18

Checks if N or more spare CP exists and any following commands are only executed if true.

Nested action branching commands are supported.

### Crafting quality action branching ending.
`Usage:` /endif

`Example:` /endif

Any command following this will be executed, regardless of the previous branching command.

### Alternate branching.
`Usage:` /else

`Example:` /else

Following commands are only executed if the previous branching command did not have a condition match.

Should only be used between a branching '/if' and '/endif' commands.

## Macro Example
To illustrate some of the commands shown above, the following macro will be used:

1. `/spareCP 28`
2. `/craft`
3. `/ac "Comfort Zone"`
4. `/ac "Inner Quiet" -trick`
5. `/ac "Waste Not" -trick`
6. `/ac "Hasty Touch"`
7. `/ac "Hasty Touch"`
8. `/ac "Hasty Touch"`
9. `/ac "Hasty Touch"`
10. `/ac "Hasty Touch"`
11. `/ac "Manipulation" -trick`
12. `/ac "Hasty Touch"`
13. `/ifquality excellent`
14. `/else`
15. <code> </code><code> </code>`/ac "Great Strides"`
16. <code> </code><code> </code>`/ifquality normal`
17. <code> </code><code> </code><code> </code><code> </code>`/ac "Innovation"`
18. <code> </code><code> </code>`/endif`
19. `/endif`
20. `/ac "Byregot's Blessing"`
21. `/ac "Careful Synthesis II"`
22. `/ac "Careful Synthesis II"`

This macro is mostly useful before the "Prudent Touch" action is learned and the crafter has access to a relatively low amount of CP (~300).

First, line 1 configures the application with the amount of spare CP that this rotation allows for given the current max amount of CP that the crafter has. The amount of spare CP can be checked after manually executing the rotation once or by using an online crafting simulator. The amount of spare CP configured (28) allows for one Hasty Touch upgrade, since an upgrade always costs 18 CP.

Line 2 tells the application to start the craft by hitting the "Begin Synthesis" button.

Lines 3 to 5 tells the application to use various crafting buffs in order (Comfort Zone, Inner Quiet, Waste Not). Lines 4 and 5 have the "-trick" option, stating that "Tricks of the Trade" can be used before these actions if the quality is good or excellent.

Lines 6 to 10 are all "Hasty Touch" action executions. If no good or excellent quality occurs at this point, the "Hasty Touch" on line 11 will be upgraded to a "Basic Touch" due to the 21 spare CP (it isn't saved for the "Hasty Touch" on line 14 because there are more "-trick" options on actions before it on lines 12 and 13, which can generate more spare CP). Otherwise, the first "Hasty Touch" that lands on a good or excellent quality will be upgraded. If "Tricks of the Trade" actions were used on lines 4 or 5, then more "Hasty Touch" actions will be upgraded.

Lines 11 executes the crafting buff "Manipulation", which also allows for extra "Tricks of the Trade" to be used. If it is, then the "Hasty Touch" on line 12 is upgraded.

Line 13 checks for the crafting quality. If it is excellent at this point, then nothing is done and the execution jumps directly to line 20 after the corresponding '/endif' on line 19, executing the "Byregot's Blessing" with the excellent crafting quality, followed by the "Careful Synthesis II" on lines 21 and 22.

However, if the quality is not excellent then the execution continues after the '/else' command on line 14. Line 15 executes the "Great Strides" buff and line 16 checks for the crafting quality again. If the quality is normal, then line 17 is executed performing the "Innovation" buff action and the execution branches are then closed. If the quality is not normal, then it has to be good or excellent, so line 17 is skipped and the execution proceeds to lines 20, 21 and 22 after the execution branches are closed. Identation was added to the macro to make it clearer which actions are inside which branching execution path.

The application then returns to the start of the macro to restart the process if necessary.

## Purchase and Updates
You can purchase the application for 2.99€ using PayPal. A download link will be sent via email automatically upon payment by FetchApp. Any bugfixes before the next major version will also be distributed for free via email.

<a href="http://atbcrafter.fetchapp.com/sell/dc75daf1"><img src="http://www.paypal.com/en_US/i/btn/btn_buynow_LG.gif" alt="Buy Now" /></a>

If you have already bought the application or obtained the application from someone else and want to contribute further for its development, you can always donate. Any amount of money helps and is appreciated.

<a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=3PTK9AH56YGPE"><img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" alt="" /></a>
