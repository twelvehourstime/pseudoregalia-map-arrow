Pseudoregalia - MapArrow mod backup
====================================

This backup is a copy of the game's Win64 folder:
  C:\Program Files (x86)\Steam\steamapps\common\Pseudoregalia\pseudoregalia\Binaries\Win64

It contains the MapArrow mod: an accessibility mod that shows a small yellow
triangle on the map (pause menu Map tab, and the quick map on D-pad up / Tab)
marking where you are inside the current room. The triangle points the way
your character is facing.


Built for
---------
  Game:         Pseudoregalia, ver. 1.272 (shown on the title screen)
  Steam build:  13615456 (app 2365810)
  Mod loader:   UE4SS v3.0.1  (https://github.com/UE4SS-RE/RE-UE4SS/releases/tag/v3.0.1)
  Made:         October 2026

If the game updates to a newer version, the mod may still work, but the map
alignment data was measured on this version. If the marker ends up in the
wrong place after an update, that's the likely reason.


What's in the backup that belongs to the mod
--------------------------------------------
  dwmapi.dll            UE4SS (mod loader) - loads automatically with the game
  UE4SS.dll             UE4SS (mod loader)
  UE4SS-settings.ini    UE4SS settings (see "Settings this game needs" below)
  Mods\mods.txt         list of enabled mods ("MapArrow : 1")
  Mods\MapArrow\        THE MOD ITSELF - the one part you can't download again
      Scripts\main.lua      the mod
      Scripts\zonefit.lua   map alignment for every area and room
      Scripts\tilemasks.lua room outlines taken from the game's map images
      README.txt            how the mod works
      calibration.txt       written by the mod (fallback alignments)
      debug.txt             written by the mod (troubleshooting log)

Everything else in the Win64 folder is the game's own files.


How to restore
--------------
Restore into:
  C:\Program Files (x86)\Steam\steamapps\common\Pseudoregalia\pseudoregalia\Binaries\Win64

  If the game is still ver. 1.272 (same version as this backup):
    Copy the whole backed-up Win64 folder back over the game's Win64 folder.

  If the game has been updated since this backup:
    Do NOT copy the whole folder back - it holds the game's old files, which
    could break the updated game. Copy back only:
      dwmapi.dll
      UE4SS.dll
      UE4SS-settings.ini
      Mods  (the whole folder)

  Then start the game through Steam as usual.


Settings this game needs (in UE4SS-settings.ini)
------------------------------------------------
These are already set in the backed-up file. Only needed if you ever install
UE4SS fresh instead of restoring this backup:
  bUseUObjectArrayCache = false     (prevents a crash on startup)
  GuiConsoleEnabled = 0             (no extra debug window)


Good to know
------------
  - Don't press Ctrl+R in game. It's UE4SS's "reload mods" key, and it
    crashes the game with this mod. Restart the game instead.
  - F10 only writes a troubleshooting log (Mods\MapArrow\debug.txt).
  - Marker size and colours can be changed at the top of
    Mods\MapArrow\Scripts\main.lua (the Config section). Restart the game
    after changing them.


How to turn it off / remove it
------------------------------
  Turn off just the mod:  in Mods\mods.txt change "MapArrow : 1" to "MapArrow : 0".
  Remove everything:      delete dwmapi.dll from the Win64 folder (that alone
                          disables UE4SS and all mods). To remove it completely,
                          also delete UE4SS.dll, UE4SS-settings.ini, UE4SS.log
                          and the Mods folder.
