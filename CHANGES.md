# FiveM Kid Friendly Mod Change List

**v0.4.1**
* Fixed NPC model replacement causing the client to crash when ambient peds spawned
* Prevented shared passenger-entry and NPC-crew hotkeys from triggering both actions

**v0.4.0**
* Added waypoint-controlled driving when riding as a passenger with an NPC driver
* Added selectable NPC passenger-driver styles with a configurable default and hotkeys
* Added recruitable NPC crews with following, vehicle, distance cleanup, player-config inheritance and optional defence handling
* Fixed vehicle spawn validation incorrectly rejecting coordinates
* Fixed an invalid NPC combat attribute causing intermittent client warnings
* Improved non-combat, flee prevention and strong ignore-player behaviour using valid NPC combat attributes
* Added behaviour-specific ped flags for ragdoll, blood pool, fleeing, evasive and friendly carjack handling
* Fixed vehicle-exit and carjack tasks being able to re-enable ragdoll on protected peds
* Kept vehicle-exit and falling ragdoll prevention independent when either option is disabled
* Improved friendly carjacking by cancelling the native carjack task before asking the targeted NPC to leave
* Added an option to disable native carjack interception independently of friendly carjack levels
* Allowed players to retarget another vehicle while a friendly carjack is being handled
* Limited passenger-side handling to NPCs occupying the target seat or blocking entry to it
* Temporarily disabled collision between the player and exiting friendly-carjack NPCs

**v0.3.0**
* Added configurable replacement of ambient NPC models
* Expanded and revised the restricted ped model list (thanks to Jaralus)
* Fixed replacement peds waiting for the wrong model to load
* Fixed player model changes retaining a stale ped handle
* Replaced task-clearing fall/vehicle-exit ragdoll prevention with temporary ragdoll suppression
* Fixed the on-fire ragdoll configuration referencing an undefined ped variable
* Added independent on-foot NPC flee prevention
* Prevented panic-driving correction from moving passengers into the driver's seat
* Fixed vehicle spawning passing a player ID where a ped handle was required
* Added timeouts and validation to player model and vehicle spawn requests
* Added basic validation to server network events
* Updated controller key mappings to use FiveM's analog-button mapper for better compatibility
* Changed `HOTKEY_VER` to `_v2` so the key mappings don't clash
* Corrected the `max_wanted_level` and `prevent_visual_carjack_passengers` config names
* Fixed loading-screen handover checks, dynamic text escaping and mixed-content font loading
* Replaced fixed loading-screen tab options with an ordered, extensible `tabs` array
* Updated the resource manifest version and declared OneSync/game build requirements
* Added a base-game configuration example with all optional modifications disabled
* Added a content-filter configuration example with reduced gore and non-destructive weapons
* Disabled default loading screen background video

Loading-screen migration: replace the old `show_tab_*` and `server_*` tab-content
settings with entries in `LS_CONFIG.tabs`. A tab's position in the array determines
its display order; remove its object to hide it. The optional `pin_to_bottom` and
`exclude_from_auto_scroll` properties replace the previous hard-coded mod-tab behaviour.

**v0.2.3**
* Fixed not teleporting inside of spawned vehicles when VEHICLES.teleport_inside_spawned is set true
* Short wait added when spawning new vehicles after purging a previous to help reduce collisions
* Implemented fixes to allow hot-restarts (restarting the script without restarting the server)
* Cloned vehicles no longer forced on to a road if called by quick spawn/spawned without the spawn inside setting
* Fixed locking time to particular hour
* Optimised handling for interior based door locking
* Improved player blip/FX handling
* Fixed mishandling of keyboard hotkeys
* Other bug fixes as per individual file changelogs

**v0.2.2**
* Fixed incorrect handling of dropped network players
* Hotkeys ignored if weapon wheel HUD currently active
* Fixed handling of the "enter vehicle as passenger" function if the driver is a player

**v0.2.1**
* **Supports OneSync** (if you previously used ```set onesync off``` in your server.cfg, change this to ```+set onesync on```)
* Added a fully configurable loading screen
* Added quick vehicle spawner (hotkey - press the set hotkey to cycle through vehicles)
* Enter an NPC's vehicle as a passenger (hotkey)
* Change the time of day and weather via the trainer
* Option to block certain doors from opening (i.e to prevent access to stripclub)
* Many function rewrites to optimise the script, including how hotkeys are handled
* Added protection against players spawning models which go against your server rules
* Failsafe to kick player if they stop this script from running
* Integrated NativeUI as part of the release (no longer a need for a separate resource)
* Fixed screen spinning when trainer opened
* Fixed trainer left and right scroll speed
* Modifiable levels of ped ragdoll prevention
* Better weapon handling, with the option to allow certain weapons
* "Parental hotkeys" fixed to protect the game timer functions
