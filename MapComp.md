# How to time map completion
The map completion category allows to subtract time you spend in loading-screens aswell as taking a break in loading-screens.
This Autosplitter makes it very easy to count only the time you are actually in control of your character.
The following Paragraphs will explain you how to set up and use the Autosplitter for this purpose specifically.

## Video Tutorial
Zotmer made a comprehensive video tutorial on the basic setup.  
You can still read on if you prefer a written version and want some advice on how to time single segments.
[![How To Time GW2 Speedruns - LiveSplit Guide](https://img.youtube.com/vi/wNML3JyVFa8/0.jpg)](https://www.youtube.com/watch?v=wNML3JyVFa8)

## Setup
0. You probably want to follow the video first and foremost. These Instructions skip over some details.
1. Install LiveSplit + this Component. (You can even have multiple installations to time different things if you want)
2. Run Livesplit and "Edit layout" -> "+" -> "Control" -> "Guild Wars 2 ..." to enable this Component.
3. Load the Splits from the pre-made files or "Edit Splits" in one of the instances.
Don't be afraid to add/delete/move the splits. They are just names with times attached to them.
4. Edit the configurations in ``Components\GW2SAB\gw2sab_config.json`` to your liking.  
This example will not count time spend in loading-screens.
```json
{
    "LoadingScreens": "exclude",
    "StartCondition": "moving",
    "PauseOnExit": "true",
    "MaxSkippedTicks":  "3"
}
```
5. (Optional) Depending on what you are doing you may also want to add your own Checkpoints in ``Components\GW2SAB\gw2sab_checkpoints.json``. You will need the ``MapID`` aswell as the ``X`` and ``Z`` coordinates for that. I used some simple [python scripts](https://github.com/Atlan-G/gw2-mumble-dev-scripts) to create the default checkpoints.
## Running
1. Open your game to character select.
2. Open LiveSplit with your layout and splits.
3. Start Recording.
3. Start Running :)  
The timers start once you move you character (maybe change ``StartCondition`` to ``notTransitioning``)
4. Take breaks to stay hydrated.  
While you are in a loading screen you can ``Alt+F4`` the game and the timer will pause.
5. Do not shut down your PC!  
If LiveSplit gets closed it's state is lost and you will need to re-time your run.  
If this happened to you, take note of your last time and follow the steps under "Timing single segemnts".
6. Resume your run by starting the game.  
After you hit enter on character select the timers will resume.
7. Once you reach 100% and receive your gifts of exploration pause the timer manually and do a ``/age``.  
If you timed both without loading screens and only loading-screen the sum should match the output.

## Timing single segments
Maybe you only want to practice one or a few maps to set up your personal bests.  
Do the following:
1. Start the Game and LiveSplit.
2. Look up the end time of the segment just before the one you want to time.
3. Set up the start time under ``Edit Splits``.
4. Enter the map you want to run.  
This will trigger a split.
5. Un-split.
6. Skip Splits until one before your segment.
7. Split manually and Run.
8. Reset to update your best segments.
