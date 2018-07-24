# ATBCrafter
The Automatic TextBox Crafter (ATBCrafter) is a FFXIV crafting utility that does not access the game's memory / process in any way and that can branch crafting actions based on quality.

The application is available for 2.99€ through PayPal. Download links are made available via email by FetchApp after payment.

<a href="http://atbcrafter.fetchapp.com/sell/dc75daf1"><img src="http://www.paypal.com/en_US/i/btn/btn_buynow_LG.gif" alt="" /></a>

## Features
- **Does not access the game's memory in any way.**
  - Only simulates key / mouse button presses and takes screenshots.
- **Detects quality during the crafting process.**
  - This allows for macros to use different actions based on quality, such as switching actions around to prevent a poor quality on the "Byregot's Blessing / Brow / Miracle".
- **Automatically detects when the next action is ready to be used.**
  - Makes crafting faster when compared to using in-game macros.
  - Prevents lag spikes from messing up the craft.
- **Handles "Maker's Mark" rotations.**
  - The number of necessary "Flawless Synthesis" can be defined and are executed in succession.
  - "Flawless Synthesis" actions can be replaced by "Tricks of the Trade" up to a defined maximum number.
- **Can craft the same item many times without human intervention.**
  - The number of times that a macro is to be executed can be defined.
  - The location of the "Begin Synthesis" button can be defined, which once detected is pressed for the next craft.
- **Actions can be tagged to have "Tricks of the Trade" used before them if the quality is good or excellent.**
  - The number of "Tricks of the Trade" used can be limited, so it can be possible to optimize a "Maker's Mark" rotation.
- **"Hasty Touches" are upgraded to "Basic / Precise Touches" based on context.**
  - The amount of spare CP that can be used to perform "Basic / Precise Touches" instead of "Hasty Touches" can be defined in a macro.
  - Tries to upgrade "Hasty Touches" that land on good / excellent qualities, so more "Precise Touches" can be used if the action is available for the best HQ chance possible.
  - The CP obtained through "Tricks of the Trade" is automatically used to upgrade "Hasty Touches".
- **Can pause, stop immediately and stop executing after the current craft.**
  - Pauses the execution when the application is focused, allowing to stop the current craft more easily.
  - When using Microsoft Windows, execution can be paused if FFXIV is not the focused application.
- **Load, Edit and Save crafting macros on the application.**
- **Highlights the action queued to be executed during crafting.**

## Cons
Since the application does not access the game's memory to obtain data about the craft, the application **requires the game to be focused** to work.
It uses the game's textbox to perform actions, mouse button presses to begin crafts and takes screenshots to detect a craft's quality.

Therefore, it also requires some configuration before it can be used. Fortunately, the configuration process only needs to be done once if the crafting log / crafting progress windows are not moved after the fact.

## Application Tour
Under Construction...

## Configuration Process
Under Construction...

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

### Performing an ingame action.
`Usage:` /ac \<action name\>

`Example:` /ac "Inner Quiet"

The specified action is copied and pasted into the FFXIV chatbox as a command to be executed.

The "Hasty Touch" action is replaced by a "Basic Touch" if crafting condition is good or excellent, or if the remaining number of "Hasty Touch" actions can all be upgraded with the amount of spare CP available. If the "Precise Touch" action is available, it is used instead if the condition is good or excellent.

`Additional option:` -trick\[:N\]

Executes "Tricks of the Trade" before if condition is good or excellent and adds 20 CP to the amount of spare CP.

If an N limit to the number of tricks is added (e.g. -trick:3), then the "Tricks of the Trade" action is not executed if there have been N previous executions. This is mostly useful for "Maker's Mark" rotations.

### "Maker's Mark" rotation handling (beta feature).
`Usage:` /flawless \<N\> \<T\>

`Example:` /flawless 12 1

Executes up to N "Flawless Synthesis" in succession, replacing up to T of them by "Tricks of the Trade". Note that the number of "Tricks of the Trade" executed prior to this command ARE taken into account towards the maximum number T, since the very first action has to be "Maker's Mark" and they will eat into the number of free "Flawless Synthesis".

**_If the "Maker's Mark" rotation can change the number of overall synthesis actions to finish a craft, it is recommended to not use this feature yet as the application may currently block waiting during execution._**

### Begin a craft.
`Usage:` /craft

`Example:` /craft

Makes the application click on the Begin Synthesis button as soon as it appears. The button should be visible when the application starts executing.


### Configuring the quality detection.
`Usage:` /qualityConfig

`Example:` /qualityConfig

Starts an infinite loop of '/ac "Observe"' command executions. Only needs to be executed until all four different crafting qualities occurr within the same synthesis, after which the user will be prompted to map each saved image to a crafting quality.

### Crafting quality action branching.
`Usage:` /ifquality (poor|normal|good|excellent)

`Example:` /ifquality excellent

Checks if crafting quality matches the specified quality and any following commands are only executed if there is a quality match.

Nested crafting quality action branching commands are supported.

Requires a prior successful quality configuration.

### Crafting quality action branching ending.
`Usage:` /endif

`Example:` /endif

Any command following this will be executed, regardless of the previous quality match.

### Crafting quality action alternate branching.
`Usage:` /else

`Example:` /else

Following commands are only executed if the previous '/ifquality' did not get a quality match.

Should only be used between the '/ifquality' and '/endif' commands.

## Macro Example
To illustrate some of the commands shown above, the following macro will be used:

1. `/spareCP 28`
2. `/craft`
3. `/ac "Comfort Zone"`
4. `/ac "Inner Quiet" -trick`
5. `/ac "Waste Not" -trick`
6. `/ac "Steady Hand II"`
7. `/ac "Hasty Touch"`
8. `/ac "Hasty Touch"`
9. `/ac "Hasty Touch"`
10. `/ac "Hasty Touch"`
11. `/ac "Hasty Touch"`
12. `/ac "Manipulation" -trick`
13. `/ac "Steady Hand II" -trick`
14. `/ac "Hasty Touch"`
15. `/ifquality excellent`
16. `/else`
17. <code> </code><code> </code>`/ac "Great Strides"`
18. <code> </code><code> </code>`/ifquality normal`
19. <code> </code><code> </code><code> </code><code> </code>`/ac "Innovation"`
20. <code> </code><code> </code>`/endif`
21. `/endif`
22. `/ac "Byregot's Blessing"`
23. `/ac "Careful Synthesis II"`
24. `/ac "Careful Synthesis II"`

This macro is mostly useful before the "Prudent Touch" action is learned and the crafter has access to a relatively low amount of CP (~300).

First, line 1 configures the application with the amount of spare CP that this rotation allows for given the current max amount of CP that the crafter has. The amount of spare CP can be checked after manually executing the rotation once or by using an online crafting simulator. The amount of spare CP configured (28) allows for one Hasty Touch upgrade, since an upgrade always costs 18 CP.

Line 2 tells the application to start the craft by hitting the "Begin Synthesis" button.

Lines 3 to 6 tells the application to use various crafting buffs in order (Comfort Zone, Inner Quiet, Waste Not, Steady Hand II). Lines 4 and 5 have the "-trick" option, stating that "Tricks of the Trade" can be used before these actions if the quality is good or excellent.

Lines 7 to 11 are all "Hasty Touch" action executions. If no good or excellent quality occurs at this point, the "Hasty Touch" on line 11 will be upgraded to a "Basic Touch" due to the 21 spare CP (it isn't saved for the "Hasty Touch" on line 14 because there are more "-trick" options on actions before it on lines 12 and 13, which can generate more spare CP). Otherwise, the first "Hasty Touch" that lands on a good or excellent quality will be upgraded. If "Tricks of the Trade" actions were used on lines 4 or 5, then more "Hasty Touch" actions will be upgraded.

Lines 12 and 13 execute a couple more crafting buffs (Manipulation and Steady Hand II), which also allows for extra "Tricks of the Trade" to be used. If it is, then the "Hasty Touch" on line 14 is upgraded.

Line 15 checks for the crafting quality. If it is excellent at this point, then nothing is done and the execution jumps directly to line 22 after the corresponding '/endif' on line 21, executing the "Byregot's Blessing" with the excellent crafting quality, followed by the "Careful Synthesis II" on lines 23 and 24.

However, if the quality is not excellent then the execution continues after the '/else' command on line 16. Line 17 executes the "Great Strides" buff and line 18 checks for the crafting quality again. If the quality is normal, then line 19 is executed performing the "Innovation" buff action and the execution branches are then closed. If the quality is not normal, then it has to be good or excellent, so line 19 is skipped and the execution proceeds to lines 22, 23 and 24 after the execution branches are closed. Identation was added to the macro to make it clearer which actions are inside which branching execution path.

The application then returns to the start of the macro to restart the process if necessary.

## Purchase and Updates
You can purchase the application for 2.99€ using PayPal. A download link will be sent via email automatically upon payment by FetchApp. Any bugfixes before the next major version will also be distributed for free via email.

<a href="http://atbcrafter.fetchapp.com/sell/dc75daf1"><img src="http://www.paypal.com/en_US/i/btn/btn_buynow_LG.gif" alt="" /></a>
