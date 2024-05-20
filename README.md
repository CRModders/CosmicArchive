# CosmicArchive
An Archive Of Every Cosmic Reach Version

<img src="/image.png"></img>

# Changelogs

## Pre-Alpha 0.1.31
- Fixed placed blocks above y=256 not saving
- Fixed huge lag spike when quitting to main menu
- Fixed item duplication bug
- Fixed a crash with the batch renderer
- Various translation improvements

## Pre-Alpha 0.1.29
- Added wooden crate
- Added gravel
- Added limestone
- Added gabbro stone
- You can now build at any height above y=0
- Inventory and hotbar are now saved
- Items are now limited, to a maximum stack size of 999x
- Significant memory and meshing optimisations
- Fixed frustum culling issues
- Introduced the 'naive' renderer, which is slower but potentially more stable for laptops
- You can now switch between the default 'batched' and the new 'naive' renderer in the settings
- Added block entity logic, with saving and loading
- Region file version has been bumped from 0 to 1
- Various translation fixes

## Pre-Alpha 0.1.28
- Added asphalt block
- Added Welsh, Serbian (also I forgot to mention Romanian from a previous update)
- Fixed wall running
- Fixed glitch-hopping when crawling near slabs
- Fixed glitching to the side of vertical slabs
- Fixed being unable to climb stairs with a vertical slab above
- Fixed block state generators not loading from the mods folder correctly
- Exposed debug info as public to java mods

## Pre-Alpha 0.1.27
- Various movement fixes
- Player no longer phases through blocks when sprinting
- Player no longer glitches into the ground when falling
- Glass stairs are no longer ugly
- Added stairs for metal panels, aluminium panels, and packed lunar soil
- Added Serbian and other localisation fixes

## Pre-Alpha 0.1.26
- Fixed glass slabs missing from the last update

## Pre-Alpha 0.1.25
- Added stairs for seamless blocks
- Added block state generators, which can create variants of blocks at startup
- `generateSlabs` is **deprecated,** please replace it with `"stateGenerators": ["base:slabs_all"]` in your data mods!

## Pre-Alpha 0.1.24
- Fixed a severe memory leak with the debug menu
- Added missing font glyphs for Croatian
- Added Bulgarian, Czech, and another dialect of Norwegian
- Various localization fixes

## Pre-Alpha 0.1.23
- Fixed a severe memory leak with the debug menu
- Added missing font glyphs for Croatian
- Added Bulgarian, Czech, and another dialect of Norwegian
- Various localization fixes

## Pre-Alpha 0.1.23
- Added Turkish, Hungarian, Danish, Sicilian, Catalan, Swedish, Croatian, Italian
- Fixed various localization issues
- Pre-alpha text will now try to fit on screen the best it can
- If text on buttons are too long, text will wrap to try to fit as well as it can

## Pre-Alpha 0.1.22
- The game has been translated to multiple languages, including Spanish, German, French, Norwegian, Dutch, Polish, Portuguese, Russian, and Ukrainian (thank you everyone for your contributions!)
- Introducing block events `base:set_cuboid`, `base:set_sphere` and `base:set_spherical_segment`
  - These block events allow for setting blocks en masse, and running triggers for each block before and after setting
  - Examples can be found in `assets/block_events/examples` in the jar file

## Pre-Alpha 0.1.21
- Made walking speed faster
- Made sprinting speed slower
- Macs can render the world now
- Fixed bug where blocks would go missing on a palette clean

## Pre-Alpha 0.1.20

- Adjusted water shader slightly
- Adjusted player physics in water
- Player walks slower now
- Potential fix for inputs being ignored when creating a new world
- Bottom of nostalgic islands world type now converts from missing to basalt stone

## Pre-Alpha 0.1.19
- Added back references to myself to the game (the guy who wrote the previous changelog has been canned.)
- Nostalgic islands now generate with stone at the bottom layer instead of lava- uh, I mean cheese.
- Got rid of foolish blocks
- Fixed bug where entering the keybinds menu would stop all keypresses from working
- Fixed the player's position not loading properly

## Pre-Alpha 0.1.18 (April Fools Update)
- FinalForEach has been cancelled so all references to him in the game have been removed.
- Added nostalgic island world type
- Added a hunger and health system for a true survival experience
- You can now eat cheese to restore health
- Added can... but no can opener (find another way to open it!)
- Added "red" "stone"
- Added Foreshadowing block
- Added a block that really doesn't want to exist
- Re-unused boombox
- Unacknowledged moonman
- Reverted atlas size increase
- Reverted reversion of atlas size increase
- Fixed worlds unloading incorrectly
- Triggers are now per-zone rather than per-game

## Pre-Alpha 0.1.17b blue
- Testing version for the block catalog for MacOS

## Pre-Alpha 0.1.17b red
- Testing version for the block catalog for MacOS

## Pre-Alpha 0.1.17
- Fixed crash on world selection screen when world seed was not set

## Pre-Alpha 0.1.16
- Added world creation screen
- Can set world name, seed, and type
- Added flat world type
- Fixed random crash with the Batched renderer
- Major internal changes, separating the concept of worlds and zones to prepare for multiplayer

## Pre-Alpha 0.1.15
- Fixed crash when chunk's palette size exceeded 128
- Palette is automatically cleaned up when exceeding a soft limit of 128 or hard limit of 4096
- Major internal refactors to prepare for multiplayer

## Pre-Alpha 0.1.14b
Unknown

## Pre-Alpha 0.1.14
- Added tickDelay to base:run_trigger
- Added debug crash button for an easy way to copy specs
- Fixed texture buffer sharing the same binding as the diffuse texture
- Fixed bug where missing blockstate id would crash when no default params specified
- Fixed open save directory bug on windows not catching AWTError

## Pre-Alpha 0.1.13d
Unknown

## Pre-Alpha 0.1.13c
Unknown

## Pre-Alpha 0.1.13b
Unknown

## Pre-Alpha 0.1.13
- Texture atlas size + precision increase using texture buffers.
- Added Max FPS Slider
- Fixed non-qwerty keybinds saving incorrectly
- Reduced max FOV to 150
- Fixed player-jittering in pause menu
- Fixed bug where zeroed view direction would freeze game
- Meshes no longer add border for null blocks

## Pre-Alpha 0.1.12g
- Adjusted atlas size for testing

## Pre-Alpha 0.1.12f
- UVs sent to the UBO are now checked for duplicates before expanding

## Pre-Alpha 0.1.12e
- Unknown

## Pre-Alpha 0.1.12d
- Unknown

## Pre-Alpha 0.1.12c
- Unknown

## Pre-Alpha 0.1.12b
- The textures atlas has been increased to 1024x, increasing the limit to 4096 different block textures (in 16x format).

## Pre-Alpha 0.1.12
- Added run_trigger to relay custom triggers
- Unlocked FPS when not using VSync
- Updates now work on a fixed-timestep tick system
- Position in debug menu now uses two decimal places
- Fixed swimming physics that behaved differently with different FPS
- Fixed being able to place or break blocks while paused

## Pre-Alpha 0.1.11
- Reverted the atlas size change.
- Reverted the UV texture precision.

## Pre-Alpha 0.1.10
- Runtime texture atlas size increased from 256x to 1024x
- Increased UV texture precision for blocks from 7 bits to 32 bits per axis
- Moved some code into save library https://github.com/FinalForEach/Cosmic-Reach-Save-Library
- Pressing ESC in the keybinds menu no longer leaves if keybind button is active
- Fixed freeze when creating world if render distance is invalid

## Pre-Alpha 0.1.9b
- A test for the inventory and open save directory button.

## Pre-Alpha 0.1.9
- Fixed vertical slab placement when not placing on the ground
- Fixed worlds not unloading on going to main menu
- Fixed bug where open directory would go to the containing folder on windows

## Pre-Alpha 0.1.8
- Added aluminium panels
- Slabs can now be orientated depending on placement position
- Removed debug printing from explosions, reducing lag
- Reduced stuttering at larger render distances
- Fixed bug on windows where the open directory buttons wouldn't open
- Fixed bug where non-english characters would crash the game

## Pre-Alpha 0.1.7
- Added C4
- All lights can toggle on interact now
- Fixed bug where light slabs being toggled would turn into full blocks
- Introduced new block event trigger: onExplode
- Introduced new block event action: base:explode
- Introduced new block event action: base:set_block_state_params

## Pre-Alpha 0.1.5d
- Changes to mesh and shader code specifically for MacOS

## Pre-Alpha 0.1.6b
- Vsync is no longer activated by default. On/Off option should properly toggle Vsync now
- Partial MacOS Support

## Pre-Alpha 0.1.6
- Added mouse sensitivity, FOV, and render distance sliders
- More work done towards mac support + a warning message that macs are not yet supported
- Selecting a block now takes into account its shape, not just its position
- Introduced the catalogHidden field for block states, hiding them from the item catalog by default

## Pre-Alpha 0.1.5c
- Fixed invisible world
- Partial MacOS Support

## Pre-Alpha 0.1.5b
- Partial MacOS Support

## Pre-Alpha 0.1.5
- Reverted the atlas size change

## Pre-Alpha 0.1.4
- Increased the runtime texture atlas size for blocks
- Block selection is now a wireframe
- Debug screen now shows the block you are looking at
- Work done towards mac support
- Keybinds should support non-QWERTY keyboards
- Fixed bug where multiple keybind buttons could be triggered at once

## Pre-Alpha 0.1.3
- Introduced Block Events, Triggers and Actions
- Fixed a bug where one of the faces on the default cube was flipped

## Pre-Alpha 0.1.2
- Pressing screenshot will notify you the file name
- Removing mods no longer corrupts the world
- Added world selection screen
- Inventory no longer duplicates items across pages
- Improved the default mouse sensitivity for wide screen resolutions

## Pre-Alpha 0.1.1
- Fixed the last item in the item catalog being unable to be added to the hotbar

## Pre-Alpha 0.1.0
- Adds packed lunar soil
- The blocks.png is overwritten at runtime, all block textures are separate files

## Pre-Alpha 0.0.14
- Fixes the last item in the catalog being omitted

## Pre-Alpha 0.0.13
- Fixed the inventory buttons not closing
- Fixed the water shader ruining the UI when escaped

## Pre-Alpha 0.0.12
- Fixed inventory slot bugs (unsure)

## Pre-Alpha 0.0.11
- Skipped Version

## Pre-Alpha 0.0.10
- Inventory pages
- Light slabs

## Pre-Alpha 0.0.9
- Fixed the last-transparent-block bug

## Pre-Alpha 0.0.8
- Fixed the menu F1 bug
- Shaders can now use an #import preprocessor

## Pre-Alpha 0.0.7
- Fixed alt-tabbing ruining the player file

## Pre-Alpha 0.0.6
- Allows all assets to be loaded from the mods folder

## Pre-Alpha 0.0.5
- Fixed crouching on slabs

## Pre-Alpha 0.0.4
- Code cleanup
- Update chunk-water shader

## Pre-Alpha 0.0.3
- Adds more error catching/logging to code

## Pre-Alpha 0.0.2
- Fixed no block destruction cool-down while in the inventory
- Added basic mod support

## Pre-Alpha 0.0.1
- Game Release
