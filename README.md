# ATBCrafter
The Automatic TextBox Crafter (ATBCrafter) is a FFXIV crafting utility that does not access the game's memory and that can branch crafting actions based on quality.

## Features
- **Does not access the game's memory in any way.**
  - Only simulates key / mouse button presses and takes screenshots.
- **Detects quality during the crafting process.**
- **Automatically detects when the next action is ready to be used.**
  - Makes crafting faster when compared to using in-game macros.
  - Prevents lag spikes from messing up the craft.
- **Can craft the same item many times without human intervention.**
  - The number of times that a macro is to be executed can be defined.
  - The location of the Begin Synthesis button can be defined, which once detected is pressed for the next craft.
- **Hasty Touches are upgraded to Basic Touches / Precise Touches based on context.**
  - The amount of spare CP that can be used to perform Basic / Precise Touches instead of Hasty Touches can be defined in a macro.
  - Tries to upgrade Hasty Touches that land on good / excellent qualities, so the best HQ chance is obtained.
  - Actions can be tagged with the "-trick" option, so if quality is good or excellent Tricks of the Trade is used before the action.
  - The CP obtained through Tricks of the Trade is automatically used to upgrade Hasty Touches.
- **Load, Edit and Save crafting macros on the application.**

## Cons
Since the application does not access the game's memory to obtain data about the craft, the application **requires the game to be focused** to work.
It uses the game's textbox to perform actions, mouse button presses to begin crafts and takes screenshots to detect a craft's quality.

Therefore, it also requires some configuration before it can be used. Fortunately, the configuration process only needs to be done once if the crafting log / crafting progress windows are not moved after the fact.
