# CosmicArchive

> [!IMPORTANT]
> Active development is moving. This repository may still receive infrequent
updates for legacy toolings. [Visit the new repo.](https://github.com/PuzzlesHQ/CRArchive/releases)

<hr>

An Archive Of Every Cosmic Reach Version

<img src="/image.png"></img>

# Changelogs

## Alpha 0.4.10
- Overhauled the cave system, adding multiple new types of caves!
- Added Rubies, which can only be found in magma caverns
- Increased ore frequency underground
- Adjusted crafting recipes of laser gun and switch to require rubies
- Removed ingots and basalt from all mob loot
- Reduced chances of getting a weapon from Incinerators and Laser Interceptors
- Fixed bug of falling into the ground when loading in the world

## Alpha 0.4.9
- Added a new item: the flamethrower: which shoots fire on the ground that constantly damages mobs
- Added a new mob: The Incinerator, an uncommon tough mob that shoots fire! When defeated, it may drop a flamethrower.
- Massively reduced fuel time of shale
- Improved `assets/post_build/dependency_lists.txt` by adding git versions of save library and localization
- Fixed placing blocks on the -X/-Z axis below
- Fixed piston UVs
- Fixed laser emitters having a directional delay
- Fixed piston push limit being 11 instead of 12
- Fixed piston heads wrongly showing up in the catalog

## Alpha 0.4.8
- Added Pistons and Suction Pistons
  - Pistons are activated by lasers and can push blocks (including block entities)
    - Suction pistons pull blocks when they retract
- Added Clay
  - Clay can be smelted into bricks
- Added shale
  - Shale can be used as fuel or be crafted into asphalt when combined with gravel
- Added new block events: `base:push_blocks` and `base:pull_blocks`
- The block event `base:replace_block_state` now has two new fields: `srcDirectionParam` (which modifies the offset) and `copiedParams` which copies parameters from the source block to the replacing block state.
- All metal storage blocks and block of rubber recipes have been changed to use only 1 item as opposed to 9
- Increased number of torches from 1 to 3 in crafting recipe
- Removed bricks and asphalt from interceptor loot table
- Various region file optimizations to decrease the size of files and prepare for future data
- Gravel no longer generates ores
- Fix bug where falling blocks would not render away from 0,0
- Fixed bug where global temperatures were too cold in world generation

## Alpha 0.4.7
- Added the Generator and the Electric Furnace
- The Boombox now has a new UI which allows it to change the note it's playing
- Overhauled the world generation
 - Temperature is no longer based on latitude, but on 2D noise instead
  - Added tectonic noise to better distribute mountains, flat areas and islands
  - Added bushes generating in forests
  - Added tooltips to the creative item catalog
- Depleted torches now drop sticks
- Reduced the volume of the jetpack noises
- Offline accounts can now have names set server-side
- Game no longer pauses when in inventory or if chat is open while the window is unfocused
- Fixed the mouse snapping when closing inventory while mouse is off-screen
- Fixed doors duplicating when blown up
- Fixed random entity lighting crash

## Alpha 0.4.6
- The default skin has been redesigned, featuring a more vibrant colour palette
- Fixed animation related crash
- Fixed crash from bad json of hungarian translation
- Fixed crashing while crafting the first time you load into a world
- The crash screen now allows for opening the save directory

## Alpha 0.4.5
- Added a jetpack, used for hovering up to 20 blocks up to aid with building!
  - The jetpack is toggled with double jump, and can be temporarily disabled by crouching
    - For now, there is no fuel requirement, but this will be added in the future
    - To use the jetpack, you'll have to equip it in your inventory first, with the slot on the far left
- The crafting menu has been overhauled, replacing grid crafting with choosing the recipe directly from the menu.
  - This is a basic implementation of the new system, and improvements will be made, and I will be looking for feedback
    - Old grid styled crafting recipes have been deprecated and while ignored for now, will not load properly in the future, please update your datamods!
- Added flying animation for creative mode
- Screenshot message is rendered at the bottom when the debug menu is opened
- Various animation fixes
- Fixed AO on blocks

## Alpha 0.4.4
- Added `updateSrcBlockState` to `base:run_trigger`
- Fixed null pointer on joining world
- Fixed players being unable to join servers they haven't before
- Potential mac fix for rendering the player in the main menu
- Fixed `rotXZ` overwriting `rotation`
- Fixed jiggly water in inventory
- Fixed block selection being affected by fog
- Fixed items disappearing on the ground
- Fixed torch rotation
- Fixed doors unsyncing their top and bottom halves
- Fixed null pointer regarding the player's cursor

## Alpha 0.4.3
- Fixed world loading getting stuck on load

## Alpha 0.4.2
- Added sounds for sand / gravel / lunar soil
- Sand and gravel are now falling blocks
- Coconuts also fall when the leaf above is broken
- Player now has a prone animation
- Can now search with the item catalog, and can now search by `tag: ` as well
- Added the laser switch, a block which when toggled either blocks lasers or lets them through


- Added `addToQueue` and `createSubqueue` fields to `base:run_trigger` block event
- Item cycling now works in multiplayer
- World generating thread now sleeps when not needed
- Server now shuts down when the ticking thread crashes
- Added `rotation` parameter to blockstates, `rotXZ` is now **deprecated**!, rewrite your datamods to support this future change
- Removed redundant `[default]` in blockstate save keys, saving around 5% of storage in new chunks
- Increased depth buffer to 24 bits


- Fixed stuttering FOV bug while sprinting
- Fixed player sinking in water when noclipped
- Fixed entities always being red after being hit in multiplayer
- Fixed entities being unlit in multiplayer
- Fixed flickering of blocks and entities when away from 0, 0
- Fixed debug menu showing "Pre-Alpha" in front of the version
- Fixed server resetting the zone of the player on reconnect
- Fixed laser guns hurting players when PvP is disabled


- Removed screenshot functionality on controllers for now to prevent the screenshot spam bug

## Alpha 0.4.1
A small hotfix patch to fix some multiplayer related issues
- Fixed being unable to join multiplayer without a custom skin
- Fixed FPS running at 10 for those who previously uncapped the frame limit
- Fixed skin loading issue on windows
- Fixed laser interceptor inaccuracy from incorrect laser refraction
- Fixed crash from deserializing skins in multiplayer
- Fixed world and networking desyncing player in server

## Alpha 0.4.0
- Added player model with custom skins!
- The skin can be previewed and set on the main menu, and can be seen by other players in multiplayer
- Can now swap items to hotbar in inventory using the number keys
- Added upside down stairs
- Added block of coal
- Added torches - an early game lighting option crafted with sticks and coal which burns out over time
- Added a void world generation option
- Added a music frequency slider to the options menu to change how often music plays


- Greatly improved the look of fog
- Improved lighting memory allocation
- Entity regions are now culled on disk where there are no entities left
- Improved controller mapping
- Items can now have tags
- canPlace predicate is now consistent with other predicates, this is a breaking change, update your data mods!
- Added queue option to base:runTrigger- this defers execution until the end of the trigger
- Increased the range of item pickups
- The Earth world generation is more flat and sharp
- Reduced the damage dealt to mobs by hitting to 1
- Adjusted ore generation so that iron and bauxite no longer spawn on the surface
- C4 drops items when exploding and damages nearby entities
- Rubber block items now are just as bouncy as their rubber item


- Various entity model UV and animation fixes
- Fixed block duplication glitch in multiplayer
- Fixed items disappearing when shift clicking into crates in multiplayer
- Fixed horrible memory leak from using a controller
- Fixed bug where you could wrongly place blocks through other blocks like vertical slabs and doors
- Fixed an invisible player issue
- Fixed laser splitters dropping debug blocks
- Fixed players stuttering while moving in multiplayer
- Fixed music lag bug


- Removed redundant id field from entity models
- Removed no clip hotkey
- Removed the naive renderer as an option
- Removed "gravel caves" from the Earth world generator, gravel spawns at the surface properly

## Pre-Alpha 0.3.27
- Added sun and moon for the dynamic sky
- Added laser splitter, which is another form of the laser emitter accessed with the cycle item hotkey
- Laser Emitters can now be pointed upwards or downwards
- Doors now stop lasers
- Held items are now visually influenced by the player's velocity
- Dropped items now take the player's velocity into account
- Rubber blocks reduce fall damage by 90%
- Lights now toggle with lasers
- Tamed interceptors now follow the player in creative
- Improved controller mapping and fixed the controller deadzone drift bug
- Server port can now be set in gameSettings.json
- Fixed bug where you get massive fall damage while wall sliding
- Fixed bug where you cannot break desynced blocks in multiplayer
- Fixed disappearing player bug in multiplayer
- Fixed lasers getting stuck visually on screen
- Fixed blocks with smaller bounds being unable to be placed in the same block as the player
- Fixed laser emitters dropping the block state depending on the direction
- Fixed laser gun crashing in null chunks

## Pre-Alpha 0.3.26
- Added fall damage
- Added crafting recipe for the laser emitter
- Improved the laser emitter model
- Traps no longer activate in creative mode
- Fixed the triangle bug and enable shared indices for all devices
- Fixed explosion particles not appearing in multiplayer
- Fixed the bug where breaking a door only broke one half
- Fixed doors generating debug blocks
- Fixed the not predicate not loading the sub predicate properly
- Fixed crash with null entity chunks

## Pre-Alpha 0.3.25
- Slightly increased the gamma of shaders
- Fixed particles glitching out on integrated GPUs
- Fixed bug where two laser emitters next to each other would crash the game
- Fixed `not` predicate being missing
- Fixed bug where particles would crash the client when made server-side
- Fixed bug where entities would randomly crash via an IndexOutOfBounds exception

## Pre-Alpha 0.3.24
- Added the Laser Emitter- a block that shoots lasers when interacted with or shot at
- Boomboxes are now triggered when lasers land on them
- Added the `random` predicate for `if` conditions.
- Can have the `percentChance` or `normalChance` parameter, which defines the likelihood of a trigger happening
- Lasers now refract in water and glass
- Interceptors no longer target the player if they are in creative
- Added the `base:block_entity_signal` block event, to tell a block entity to perform an action
- Saplings now use a 2D model for the held item
- Spawning items from the item catalog synchronizes in multiplayer properly
- Various 'if' predicate fixes
- Fixed lasers having buoyancy

## Pre-Alpha 0.3.23
This one is a little bit special, it comes with an animated trailer by @JoeFly ! Send him some appreciation!
TBD: include trailer
- Added the Laser Interceptor, a slightly uncommon drone which shoots lasers at you from a distance!
- Increased durability of laser guns to 500 uses
- Laser projectiles now use the onLaserHit block event trigger rather than onExplode
- Laser particle texture is now white and tinted via the particle system
- Asset loading now supports subfolders in asset paths and ids
- Fixed crash with multiple C4 Explosions at once
- Fixed particle acceleration not resetting for y and z axis
- Fixed particles crashing upon serialisation in multiplayer

## Pre-Alpha 0.3.22
- C4 now has particles when blowing up
- Added laser gun
- Can shoot lasers at C4 to blow up from afar
- Fixed bug where flying players would be treated as perpetually falling server-side
- Fixed multiple issues regarding entities loading in and hitboxes

## Pre-Alpha 0.3.21
- Added `defaultProperties` to block states
- Can now screenshot when chat is opened
- Added `has_param`, `has_block_id`, `has_blockstate_id` as predicates for block states (such as `srcBlockState` and `block_at`)
- Added `COSMIC_REACH_USE_SHARED_INDICES` environment variable
- Fixed predicates "falling through", such that an `and` always triggers an `or`, which always triggers an `xor`
- Fixed door models and UVs
- Fixed seamed stair UVs
- Fixed poplar leaves wrongly dropping items in creative
- Fixed Mac not rendering
- Fixed shader validation wrongly erroring on comments
- Fixed shaders not handling CRLF properly

## Pre-Alpha 0.3.20c
- Unknown changes. MacOS testing version.

## Pre-Alpha 0.3.20b
- Unknown changes. MacOS testing version.

## Pre-Alpha 0.3.20
- Added doors
- Interceptors now have emissive textures
- Interceptors now change textures via animations rather than code directly
- Friendly interceptor traps now have a consistent colour with the flying interceptors
- Gold ore texture is now consistent with the bar and block textures
- Fixed jump running being dependent on FPS
- Disabled shared indices on non-Nvidia GPUs
- Improved batch renderer reliability
- Blocks no longer drop in creative

Notes for data modding:
- Added new block event: base:copy_block_state_params- this copies parameters from one block to another
- Added new block event: base:cycle_block_state_params- this cycles between parameter values
- Added if condition to block events. A block event will only trigger if the condition is true.
- Added condition root: srcPlayer: information about the player who caused the trigger, if any
- Has gamemode: information about the gamemode of a player
- Has allows_items_drop_on_break: Whether the gamemode is allowed to drop items when a block is broken
- Added condition root: srcBlockState: information about the block causing the trigger
- Has has_tag: Whether a blockstate contains a tag or not
- Added condition root: block_at: information about a block at a given position
- Treated the same as the blockstate condition, but has xOff, yOff, and zOff parameters
- The canPlace predicate is subject to change to be more in line with the if conditions, so be aware!


## Pre-Alpha 0.3.19b
- Player moves fast on ice while jumping again
- UI changes colour with world lighting when inventory is closed
- Can jump on a single block without overshooting
- Prevent crash when text display cannot find the underlying blockstate
- Fixed ingot textures having semitransparent pixels

## Pre-Alpha 0.3.19
- Fixed being stuck jumping in a single direction
- Fixed items being flicked in the wrong direction
- Increased FOV while sprinting

## Pre-Alpha 0.3.18
- Fixed movement speed being hardcoded for 60FPS

## Pre-Alpha 0.3.17
- Added randomized pitch to sound block events (breaking / placing)
- Rubber balls now bounce on the ground
- Changed ingot textures
- Forests now have different tree densities
- Entity momentum is now preserved properly
- Added day counter to F3 menu
- Tick 0 is now the morning rather than noon
- Added launcher name to crash screen via environment variable `COSMIC_REACH_LAUNCHER_NAME`
- Crouching in water descends the player faster
- Reduced rapid creation of new entity chunks when entities fall into the void
- Fixed font for non-english characters
- Reduced hardness of tree logs
- Got rid of font size limit on TextModelInstance

## Pre-Alpha 0.3.16
- Added Block of Gold
- Changed the colour palette of gold ingots and gold medkits
- Added `/clear` command to clear the inventory of a player
- Language button is now an icon on the bottom right of the main menu
- For modders: RuntimeInfo.java has a String field called `gameVariant` for modloaders to override.
- `xor` condition added for canPlaceChecks and crafting recipes
- Can now set the offline name via an environment variable: `COSMIC_REACH_OFFLINE_DISPLAY_NAME`
- Fixed the preamble screen moving the ok button depending on screen size
- Fixed credits menu not fast-forwarding when holding space or control
- Fixed crashes relating to where the player was looking at blocks

## Pre-Alpha 0.3.15
- Added Latex, extracted when you use the fluid vacuum on a tree log
- Added rubber blocks, a block which bounces you when you fall on it
- Added bounciness field to block states
- Added /post_build/dependency_lists.txt to .jar file
- For modders: added music packets to change the song playing client-side
- Item use is now server-side
- Split vertical slabs into seamed and seamless versions ( For data mods, this is a breaking change, update your blocks, look at base blocks for examples! )
- No longer have zero friction when no-clipping mid-air
- Fixed medkits not working in multiplayer
- Fixed entities in the same chunk as the player not loading
- Fixed water items not rendering when dropped
- Fixed the UV of the negative Z-axis face being flipped
- Pick block in creative mode no longer gets 100x items
- Fixed bug where non-english text would not render on signs
- Fixed logging using the wrong year format
- Fixed commands being unable to display multiple lines in multiplayer
- Fixed /kill not working in creative
- Fixed client-side crashing on null world

## Pre-Alpha 0.3.14
- Hotfix to fix server crashes when unloading text displays
- Hotfix to fix mac crashing when loading the text display shader

## Pre-Alpha 0.3.13
- Added 'Text Displays', a sign which can change colour and size of the text
- Added /playercount and /who commands
- Fixed only 4 out of 11 songs being played... now enjoy the rest of the soundtrack!
- Fixed chat messages being able to contain new lines
- Fixed various block UV rotation issues

## Pre-Alpha 0.3.12
- Added music, with 11 different tracks by 4 different artists
- Added sliders in the option menu for music and sound
- Added ice
- Added /say command
- Added friction field for block states
- You can now smelt ice and snow in the furnace to get water
- Disabled item catalog for survival players
- The block for Aluminium has been renamed to Block of Aluminium for English
- @Language Contributor make sure you treat the Aluminium translations in the same way

## Pre-Alpha 0.3.11
- Hotfix to fix the game crashing without an Itch API key

## Pre-Alpha 0.3.10
- Fade-out fog and environmental fog are now two different things
- Less fog shadow when terrain is higher
- Items and mobs are now affected by fog
- Improved chunk loading order
- Chat no longer stores duplicate entries
- Use int instead of float for packed numbers on non mac systems
- Added `effectiveBreakingTags` to item data
- Last multiplayer address is now saved
- Fixed missing top chunks while generating world
- Fixed crash while drawing text of null strings
- Fixed localization credits missing
- Fixed world creation freezing when itch account does not login on time

## Pre-Alpha 0.3.9
- Fixed crash when starting game for AMD and Intel graphics
- Fixed offline accounts being unable to save in singleplayer

## Pre-Alpha 0.3.8
- Contribution: Player usernames now appear above the player!
- Added fog
- Minor batch rendering optimization
- Disable shared indices for windows intel iGPU (potential temporary fix for integrated graphics issues)
- Fixed windows hosted multiplayer servers not saving players
- Fixed random crash when exiting to the main menu

## Pre-Alpha 0.3.7
- Added the fluid vacuum
- Added sounds for wood and glass-like blocks
- Added `/zonespawn` command
- Water blocks can now be placed on other water blocks
- Can now uncraft packed lunar soil
- Adjusted interceptor drops: fewer medkits, more blocks
- Items now prioritize slots with existing stacks when picked up
- Fixed bug where player would desync on respawn
- `base:set_block_state_params` now works on the target block rather than the event source block
- Servers no longer accept unknown blocks
- Servers now reject multiple protocol syncs
- Servers now silently ignore connection resets from the client
- @Language Contributor A new translation key for the fluid vacuum has been added. Also as per the recent Japanese language additions, many characters are yet to be added in the font files, additions welcome!

## Pre-Alpha 0.3.6
- Fix authenticating handshake while connecting to servers for the executable builds via the itch client

## Pre-Alpha 0.3.5
__Servers *must* update in order to play in non-offline mode.__
- Fixed /tp command breaking in singleplayer
- Added server setting for enabling/disabling pvp
- The tick running and world loading threads will now sleep when no one is online
- The tick running thread will now sleep in between ticks instead of busy-waiting
- Chat is now cleared when leaving a world or server
- Fixed mouse disappearing when disconnecting from server
- **Security**: Packets from unauthenticated clients are now rejected.
- **Security**: The authentication server is now HTTPS. This is a breaking change for multiplayer, previous versions can no longer authenticate as a result.

## Pre-Alpha 0.3.4
- Potential fix for infinite loading on clients joining servers
- Fixed singleplayer being unable to use commands

## Pre-Alpha 0.3.3
- Fixed server crash on startup

## Pre-Alpha 0.3.2 (The Multiplayer Update)
- Added Multiplayer
- Added account authentication
- Servers can whitelist, add operator status and ban players
- Added ban, ban-ip, unban, unban-ip, kick, op, and de-op commands
- Commands are now synchronized
- Server settings can have a default gamemode for players
- Server now only sends entity positions when they change
- Added brick blocks

And now for the notable changes of the previous discord-only pre-releases leading up to this one:
- Fixed credits using the wrong charset
- Flying downwards in no-clip is now the same speed as going up
- Fixed block loot drops not dropping on center
- Fixed backspace in chat not deleting on the cursor
- Fixed creative mode consuming blocks in inventory
- Item catalog gives different amounts depending on if shift clicking or not
- Fixed a bug where block with inverted normals had no bounding box
- Air blocks have their own block event separate from default
- The environment variable ITCHIO_API_KEY will now accept itch API keys as well as JWT keys

Also, @Lee I officially owe you a game of SCP. Yes, this is an important part of the changelog, you know why.

## Pre-Alpha 0.3.2-pre10
*I'm almost certain this is the last before the official release, just need to do some config setup + auth if nothing goes wrong*
- Air blocks now have their own block event separate from default
- Fixed client being unable to load in singleplayer
- Mobs can now attack the player in multiplayer
- Players with Itch accounts can now save in multiplayer
- `ITCHIO_API_KEY` will now accept itch API keys as well as itch JWT keys

## Pre-Alpha 0.3.2-pre9
- Player doesn't spawn in multiplayer until the world is fully loaded for the render distance
- Various stability fixes

## Pre-Alpha 0.3.2-pre8
- Quick hotfixes to make the world loader more stable

## Pre-Alpha 0.3.2-pre7
*This is probably the **last** discord-only pre-release before the official update is made available to all.*
- Fixed interacting with inventory in singleplayer causing crash
- Fixed rare crash when saving
- Block breaking sounds are now no longer wrongly global in multiplayer
- Fixed crates dropping ghost items
- Fixed bug where a block with inverted normals had no bounding box
- Added loading screen for multiplayer
- Entities are now in multiplayer
- Massively improved multiplayer chunk loading
- If a client uses a lower distance than the server, the server will not send more chunks than necessary
- Can now drop + flick items in multiplayer
- Furnaces are now working in multiplayer
- Fixed random exceptions with the player position packet
- Entering multiplayer is less error prone

## Pre-Alpha 0.3.2-pre6

- 2D and 3D sounds are now networked
- Added ticking on servers
- Fixed block loot drops not dropping on center
- Backspace now deletes on cursor, not at end
- Creative mode blocks don't decrease when placed
- Item catalog now gives different amounts depending on if shift clicking or not
- Crates are now networked
- Fixed bug where could not place blocks above top loaded chunk on servers
- When pasting, replace the default text in multiplayer address field
- Fixed crash when pasting in multiplayer address

## Pre-Alpha 0.3.2-pre5
Another discord-only development release, to hold you over for those who really can't wait for the fully fledged update.
- Fixed being unable to break leaves in multiplayer
- Disconnects are handled properly
- Fixed english tips being replaced by hungarian ones
- No clip flying down is now the same speed as flying up
- Fixed block positions causing crashes in negative coordinates

## Pre-Alpha 0.3.2-pre4
- Fix default path for windows causing crash on first save
- **This server is compatible with 0.3.2-pre2 clients**

## Pre-Alpha 0.3.2-pre3
- Potential fix for windows
- **This server is compatible with 0.3.2-pre2 clients**

## Pre-Alpha 0.3.2-pre2
Another discord-only development release, to hold you over for those who really can't wait for the fully fledged update.
- Chat is limited to 256 chars per message
- Fixed credits using the wrong charset
- Join message whenever a player enters the server
- Server uses jar location to store worlds + config
- Can break, place and interact with blocks in servers now. (some block events are only partially implemented)
- Various networking crashes fixed

## Pre-Alpha 0.3.2-pre1
This is a discord-only development release intended for modloaders to adapt to the new systems for multiplayer. Multiplayer will not function properly outside of basic actions like moving around.
- Added basic multiplayer via netty
- The client save directory is used, and the server cannot be configured yet
- All clients + server must have the same mods for expected results
- No account auth is used yet.

## Pre-Alpha 0.3.1
- Fixed axes not being effective towards wooden crates
- Fixed sounds not loading from their resource locations
- Fixed credits screen crashing
- Better error handling on block events
- Better logging on block state generators

## Pre-Alpha 0.3.0
- All mods and assets are now namespaced, data mods must be in the path `/mods/YOUR_NAMESPACE/YOUR_ASSET_FOLDER/YOUR_ASSET`
- For example, if I added a banana item, it would be under the path in the save directory `/mods/my_banana_mod/items/banana.json`
- Please refer to the base assets as examples on how to migrate your data mods to 0.3.0
- Items now have tooltips
- Credits scroll faster when holding the sprint or jump keybinds
- Tools are only damaged if blocks have a hardness greater than 0
- Saplings no longer block light
- Normals on saplings are now fixed
- Saplings can only plant on valid blocks now
- Added `canPlace` predicate to sapling
- Dropped block_ prefix from block json file names
- Moved `isTransparent` and `cullsSelf` flags to from blockstate to model files
- Models and textures are now referenced by their identifier in files
- Refactored language files to support tooltips and mods, added translation keys for blocks and items

## Pre-Alpha 0.2.5
- Added /skylight command
- Added credits screen
- Added community contribution: 3D Item models
- Reduced frequency of iron ore generation
- Poplar trees now have their own leaves and saplings
- Added new block event: `base:loot_drop` which allows blocks to have a custom loot table

## Pre-Alpha 0.2.4
- You can now paste seeds directly in the world creation screen
- The cursor now resets to the center of the screen when opening the inventory
- Fixed nostalgic islands world type never loading in
- Fixed mesh glitches when too many blocks are edited at once
- Fixed a bug where a single-block layer would upgrade to a bit layer with the wrong block
- Fixed respawning whenever the game restarts
- Fixed camera getting stuck looking straight down when away from the world origin

## Pre-Alpha 0.2.3
- Fix player respawning every time the world is loaded

## Pre-Alpha 0.2.2
- Fix crash in F3 debug menu when not looking at blocks
- Potential fix for cropped screenshots on certain mac computers

## Pre-Alpha 0.2.1
- Reduced vertex size
- Reduced in-memory representation of blocks and world sizes on disk
- Remove metal blocks from interceptor loot
- Fix spawn point to be dependent on the world seed
- Fixed world spawn being set in the air or in water
- Fixed bug where player is spawned with 10 out of 3 max HP
- Fixed block selection being interrupted while moving
- Fix mod asset loading for windows (Testers wanted!)
- Potential screenshot fix for mac (Testers wanted!)

## Pre-Alpha 0.2.0
- Added the new "Survival" world type
- Added `/time` command
- Added Poplar trees
- Added per-face normals, and blocks are now lit by the position of the sun
- Added iron and aluminium tools
- Added block hardness
- Spawn position is now random in a 5000 block radius from 0, 0
- Default sky for non-moon worlds is now dynamic, temporarily removed the lighting options
- Fixed bug freezing player on first world load
- Fixed falling through the floor when away from the original camera position on load
- Fixed modded items and recipes not loading on windows
- Removed `generateSlabs` flag from block states

## Pre-Alpha 0.1.50
- Fix crashing on breaking block in new world
- Fix crash on modded item overwriting an existing one

## Pre-Alpha 0.1.49
- Added item durability
- Furnaces now explode when smelting C4
- Temporarily added a rare chance for interceptors to drop gold ingots
- Allied interceptors are now cyan instead of green
- Furnace screen now closes when the furnace is broken
- Fixed modded items + recipes not loading in
- Fixed crash when a missing block is replaced with a modded item

## Pre-Alpha 0.1.48
- Items, furnace recipes, crafting recipes, and loot now load from data ( and data mods! )
- Player now starts at 3 max HP
- Added gold, aluminium, and iron for both ores and ingots
- Added a gold medkit, which increases your max HP by 1 up to a max of 10
- Can now tame interceptors using a gold ingot
- Can now double jump in creative to go into no-clip
- Sticks now take two planks instead of one
- Fixed player freezing upon teleporting or respawning
- Fixed bug where a crash would occur on absurd amounts of leaves
- Fixed furnace dropping its lit variant
- Fixed furnace being lit with a non fuel item in fuel slot
- Fixed bug where shift clicking into furnace caused a crash
- Fixed duplication bug when pressing drop item key in the crafting output
- Added a crash guard as a temporary fix until a rare bug with large amounts of meshes can be diagnosed

## Pre-Alpha 0.1.47
- Fixed tools not working

## Pre-Alpha 0.1.46
- Added a furnace
- Takes logs, planks, sticks, leaves, wooden crates, or magma as fuel
- Can smelt sand into glass, and stone into magma
- Added `/nightvision` command
- Added short aliases for commands (use the `/help` command for more details)
- Inventory UI now has higher contrast
- The world now saves its current time
- Fixed a huge lag spike when placing or breaking blocks near rainbows (_yes really_)
- Fixed a bug where clicking an empty item slot may crash the game
- Fixed severe flickering of water and leaves in the batch renderer

## Pre-Alpha 0.1.45
- Added block tags (For data modders: an arbitrary list of strings called `tags` in a blockstate)
- "Flicking" an item on the ground now plays a small sound
- Fixed a bug where selecting a different block would not reset the breaking timer
- Fixed the bug where player would freeze on making a new world
- Fixed ghost transparent blocks in the batch renderer
- Fixed bug where cursor slot had the wrong perspective for an item
- Fixed shifting clicking crafting outputs not stacking + output slot is now coloured differently
- Fixed sticks not stacking
- Fixed rare crash when breaking animation is exactly one
- Allow survival mode players to disable no-clip via hotkey
- Fixed shovels not being effective towards dirt
- Fixed missing block related crash when breaking with tool

## Pre-Alpha 0.1.44
- Added crafting system
- Added "2d" items
- Added medkit
- Added stick
- Added stone axe, pickaxe, and shovel
- Added `/die` command
- Added `/teleport` command
- Added `/gamemode` command (Use `/gamemode creative` and `/gamemode survival`)
- Can no longer instant-break blocks in survival mode
- Hitting items on the ground knocks them back
- Dynamic sky colour is now brighter on the horizon
- Chat text shadow is now darker
- Can no longer no-clip via hotkey in survival
- Fixed bottom of water clipping
- Adjusted metal panel + drone textures to be more saturated
- Debug screen shows bounding boxes of entities

## Pre-Alpha 0.1.43
- Held item is now independent of FOV
- Made picking up items easier
- Random ticks now only occur in immediately surrounding regions
- Fixed a bug where the player would freeze when making a new world
- Fixed item jitter
- Added commands, notably /noclip and /summon
- Sprinting now influences the FOV
- Adjusted sprinting and walking speed
- Fixed a rare batch rendering crash

## Pre-Alpha 0.1.42
- Fixed the stars spinning like crazy.

## Pre-Alpha 0.1.41
- The currently selected item is now shown in your first person "right hand".
- Support non english world names
- Fixed bug where you could drop the wrong hotbar item if the cursor is hidden and hovered over
- The world loader thread now sleeps when idle
- Really really long world names are truncated in the world selection menu
- Fixed leaf decay crash
- Item drops float when "inside" blocks
- Can pick up items one block up
- Stars now rotate in the Dynamic sky
- Gravity is stronger, the player is now less "floaty"
- Crates drop items when destroyed
- Items correctly display "0" when count is 0, and no longer display if count is 1.
- @Language Contributor  Localized the percent format for the loading screen
- Fixed the drone texture
- Camera far clipping plane now shrinks with lesser render distances

## Pre-Alpha 0.1.40
- Blocks now drop as items
- New block event: `base:item_drop`, which can take in a position and optionally `dropId` as an input parameter
- Picking block now chooses the "correct" block state
- Pressing the drop item key in the inventory can drop the item in the hovered slot
- Stairs and vertical slabs now placed based on camera orientation rather than raycast position
- Fixed freeze when picking up similar items in inventory
- Fixed being unable to reliably leave water when swimming
- Worlds are now sorted by last played
- All saved strings + files use UTF-8 wherever possible
- Fixed being able to go fullscreen with the mouse causing the game to be unplayable

## Pre-Alpha 0.1.39
- Fixed placed coconuts despawning after some time instead of growing trees
- Fixed leaf blocks growing into trees
- Fixed being unable to shift-click items when the hotbar is full

## Pre-Alpha 0.1.38
- Added coconut trees
- The nostalgic islands world type is now the default
- Added random ticks, available now in block events with the `onRandomTick` trigger
- Added the `base:increment_param` block event action
- Fixed storage screen flickering on the first frame
- Fixed being able to drop an item from another world
- Meshing optimizations
- Clicking outside of the inventory drops the cursor's item
- Clicking in the item catalog now deletes the cursor's item
- Health bar now flashes when dropping
- Fixed game not pausing after loading if window unfocused
- Drones no longer drop dirt, grass or tree logs

## Pre-Alpha 0.1.37
- Added a flying drone called the Interceptor
- Added a trap which spawns Interceptors
- Added a death screen
- Added damage effects
- Improved the main menu
- Added a difficulty setting: Currently only peaceful and normal are used.
- Can now drop items out of the inventory
- Fixed crash when creating a new world or respawning
- Fixed lighting calculations
- Moved game tick updates to a separate thread
- Fixed random frame-dependent camera jitter
- Fixed background threads not closing properly when the game crashes
- Region file version bumped to version 2
- Game can now save and load entities

## Pre-Alpha 0.1.36
- Fixed bug with black screen on creating a new world
- Fixed bug where cycling item types of a missing block would cause a crash

## Pre-Alpha 0.1.35
- Fixed bug where world would crash upon entering

## Pre-Alpha 0.1.34
- Can now cycle block types in hotbar, e.g. blocks/slabs/stairs (set to the " ` " keybind by default)
- Can now set the save game directory with command line option -s or --save-location
- World info now stores additional metadata
- Added 3D audio, with new play_sound_3d block event
- Fixed a bug where picking a missing block would cause a crash
- Fixed a bug where changing worlds would show a black screen until pausing
- Fixed bug where dropping an item could not be rebound to mouse buttons
- Fixed a regessing bug where the last transparent block in a chunk would still be visible after removal
- Space keybind is no longer blank when set
- More internal work on mobs

## Pre-Alpha 0.1.33
- Small hotfix to fix crashing when opening a crate
- Various translation fixes

## Pre-Alpha 0.1.32
- Added the "Dynamic Sky" lighting option
- Added mouse keybinds for placing / breaking blocks
- Slight inventory improvements
- Max stack size increased to 1000, displayed as 1K
- Breaking blocks adds it back to your inventory
- Significant batch renderer optimizations
- Improved the internal block entity API for modders
- Mac vertex format is now the same as on PC
- Various translation additions
- Added health bar
 
## Pre-Alpha 0.1.31d
Unknown. MacOS test version

## Pre-Alpha 0.1.31c
Unknown. MacOS test version

## Pre-Alpha 0.1.31b
Unknown. MacOS test version

## Pre-Alpha 0.1.31
- Fixed placed blocks above y=256 not saving
- Fixed huge lag spike when quitting to main menu
- Fixed item duplication bug
- Fixed a crash with the batch renderer
- Various translation improvements

## Pre-Alpha 0.1.30
- Hotfix to prevent worlds regenerating terrain and reverting placed blocks

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
