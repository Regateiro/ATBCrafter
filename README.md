# ATBCrafter
The Automatic TextBox Crafter (ATBCrafter) is a FFXIV crafting utility that does not access the game's memory and that can branch crafting actions based on quality.

## Features
- **Does not access the game's memory in any way.**
  - Only simulates key / mouse button presses and takes screenshots.
- **Detects quality during the crafting process.**
  - This allows for macros to use different actions based on quality, such as switching actions around to prevent a poor quality on the _Byregot's Blessing / Brow / Miracle_.
- **Automatically detects when the next action is ready to be used.**
  - Makes crafting faster when compared to using in-game macros.
  - Prevents lag spikes from messing up the craft.
- **Can craft the same item many times without human intervention.**
  - The number of times that a macro is to be executed can be defined.
  - The location of the _Begin Synthesis_ button can be defined, which once detected is pressed for the next craft.
- **Actions can be tagged to have _Tricks of the Trade_ used before them if the quality is good or excellent.**
  - The number of _Tricks of the Trade_ used can be limited, so it can be possible to fully automate a _Maker's Mark_ rotation.
- **_Hasty Touches_ are upgraded to _Basic / Precise Touches_ based on context.**
  - The amount of spare CP that can be used to perform _Basic / Precise Touches_ instead of _Hasty Touches_ can be defined in a macro.
  - Tries to upgrade _Hasty Touches_ that land on good / excellent qualities, so more _Precise Touches_ can be used if the action is available for the best HQ chance possible.
  - The CP obtained through _Tricks of the Trade_ is automatically used to upgrade _Hasty Touches_.
- **Can pause, stop immediately and stop executing after the current craft.**
  - Pauses the execution when the application is focused, allowing to stop the current craft more easily.
  - When using Microsoft Windows, execution can be paused if FFXIV is not the focused application.
- **Load, Edit and Save crafting macros on the application.**
- **Highlights the action queued to be executed during crafting.**

## Cons
Since the application does not access the game's memory to obtain data about the craft, the application **requires the game to be focused** to work.
It uses the game's textbox to perform actions, mouse button presses to begin crafts and takes screenshots to detect a craft's quality.

Therefore, it also requires some configuration before it can be used. Fortunately, the configuration process only needs to be done once if the crafting log / crafting progress windows are not moved after the fact.

## Configuration Process
Under Construction...

## Available Macro Commands
Under Construction...

## Purchase
You can purchase the application for 2.99€ using PayPal. A download link will be sent via email automatically upon payment by FetchApp. Any bugfixes before the next major version will also be distributed for free via email.

<a href="http://atbcrafter.fetchapp.com/sell/dc75daf1"><img src="http://www.paypal.com/en_US/i/btn/btn_buynow_LG.gif" alt="" /></a>
