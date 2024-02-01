# WoW Addon Utilities

A collection of functions used in my World of Warcraft© addons which might hopefully prove to be useful to other addon developers as well; _feel free to use these in your own addon projects_.  
Each LUA file of this repository is about a specific WoW topic and contains methods and constants related to that topic. See [Repository contents](#repository-contents) for a complete overview.

**Note:** _This is not an addon nor a LibStub library!_
&nbsp;  

## Usage

There are multiple ways to include these utility files into your project. Here are some examples:

### 📦 Download and Copy

1. Download the whole package or just the file you need from this repo.
2. Extract ZIP file or copy single file into a folder inside your project's directory.
3. Add a reference to the file(s) in your addon's TOC file.
4. Use in your LUA files, eg. as follows:

    ```lua
    local AddonID, ns = ...
    -- 'ns.utils' holds all utilities
    -- 'ns.utils.achieve' holds all achievement related utilities, etc.
    ```

### 📝 Add to PKMETA File

Copy the below snippet into your `.pkmeta`/`pkmeta.yml` file:

```yaml
externals:
    utils: https://github.com/erglo/wow-addon-utilities.git
    # 'utils' is the name of the folder in your project where you keep the
    # utility files; this is merely a name I chose.
```

### 🔗 Include as a Git Submodule

```bash
# Links the submodule with folder "dir_name"
git submodule add https://github.com/erglo/wow-addon-utilities.git [dir_name]
# Copies all files from the submodule into "dir_name"
git submodule update --init
```

### ♻️ Clone this Repository

```bash
git clone https://github.com/erglo/wow-addon-utilities.git
```

----

## Repository Contents

- **achievements.lua** (`ns.utils.achieve`) - A collection of utilities handling achievements.
  + `.GetWrappedAchievementInfo(achievementID, raw)` &rarr; `achievementInfo`: _table|nil_  
    A key-value wrapper for [GetAchievementInfo()](https://wowpedia.fandom.com/wiki/API_GetAchievementInfo).
  + `.GetWrappedAchievementCriteriaInfo(achievementID, criteriaIndex, raw)` &rarr; `criteriaInfo`: _table|nil_  
    A key-value wrapper for [GetWrappedAchievementCriteriaInfo()](https://wowpedia.fandom.com/wiki/API_GetAchievementCriteriaInfo).
  + `.GetWrappedAchievementNumCriteria(achievementID, includeCompleted)` &rarr; `numCriteria`: _number_, `numCompleted`: _number|nil_  
    Retrieve the total and optionally the completed criteria number for given achievement.
  + :new: `.GetAchievementLinkWithIcon(achievementInfo)` &rarr; `achievementLink`: _string_  
    Generate an achievement hyperlink with an icon in front of it for given wrapped achievement.
  + `.IsAchievementCompleted(achievementID)` &rarr; `isCompleted`: _boolean_  
    Check whether given achievement has been completed.
  + `.IsAssetCriteriaCompleted(achievementID, assetID)` &rarr; `isCompleted`: _boolean_  
    Check if the criteria of given asset has been completed for given achievement.
  + `.GetAchievementCriteriaInfoList(achievementID)` &rarr; `criteriaInfoList`: _table_  
    Retrieve all wrapped criteriaInfo for given achievement.
  + `.GetMainCategoryInfoList()` &rarr; `mainCategoryInfoList`: _table_  
    Retrieve a list of wrapped categoryInfo of the main achievement categories.

- **currencies.lua**
  + TODO - Add currency handler

- **handynotes.lua** (`ns.utils.handynotes`) - A collection of utilities for HandyNotes plugins.  
  ⚠️**Requires:** [HandyNotes](https://www.curseforge.com/wow/addons/handynotes "Visit CurseForge.com")
  + `:GetCoordFromXY(x, y)` &rarr; `coord`: _number_  
    Get the HandyNotes coordinates from given x/y position numbers.
  + `:GetXYFromCoord(coord)` &rarr; `x`: _number_, `y`: _number_  
    Get the x/y position from given HandyNotes coordinates number.
  + `:GetPlayerMapCoord()` &rarr; `mapID`: _number|nil_, `coord`: _number|nil_  
    Get the uiMapID and the HandyNotes coordinates from the player's current position.
  + `:SetMapCoordUserWaypoint(mapID, coord, chatNotifyOnError)` &rarr; `success`: _boolean_  
    Set a user waypoint on given map at given HandyNotes coordinates. The optional "chatNotifyOnError" informs the user additionally in chat that given map doesn't support waypoints (on screen by default).
  + `:GetUserWaypointMapCoord()` &rarr; `mapID`: _number|nil_, `coord`: _number|nil_  
    Get the uiMapID and the HandyNotes coordinates from a user waypoint.
  + :new: `:ClearUserWaypoint()`  
    Remove a previously set user waypoint.

- :new: **libqtip.lua** (`ns.utils.libqtip`) - A collection of wrapper for the LibQTip-1.0 library.  
  ⚠️**Requires:** [LibQTip-1.0](https://www.curseforge.com/wow/addons/libqtip-1-0 "Visit CurseForge.com")  
  + `:AddBlankLineToTooltip(tooltip, ...)`  
    Add a new empty line to the bottom of the LibQTip tooltip.
  + `:AddColoredLine(tooltip, FontColor, ...)`  
    Add a new line with text in given font color to the bottom of the LibQTip tooltip.
  + `:AddDisabledLine(tooltip, ...)`  
    Add a new line with GRAY text to the bottom of the LibQTip tooltip.
  + `:AddErrorLine(tooltip, ...)`  
    Add a new line with RED text to the bottom of the LibQTip tooltip.
  + `:AddHighlightLine(tooltip, ...)`  
    Add a new line with 'highlighted' (white) text color to the bottom of the LibQTip tooltip.
  + `:AddInstructionLine(tooltip, ...)`  
    Add a new line with GREEN text to the bottom of the LibQTip tooltip.
  + `:AddNormalLine(tooltip, ...)`  
    Add a new line with 'normal' (golden) text color to the bottom of the LibQTip tooltip.
  + `:SetTitle(tooltip, ...)`  
    Add a new header line with 'highlighted' (white) text color and a slightly bigger font size to the bottom of the LibQTip tooltip.
  + `:SetColoredTitle(tooltip, FontColor, ...)`  
    Add a new header line with text in given font color and a slightly bigger font size to the bottom of the LibQTip tooltip.
  + `:AddQuestTagTooltipLine(tooltip, tagName, tagID, worldQuestType, color, iconWidth, iconHeight, ...)`  
    Add a new line with given quest type tag in 'normal' (golden) text color to the bottom of the LibQTip tooltip.
  + `:CopyGameTooltipTo(tooltip, FontColor)`  
    Copy the GameTooltip's left side text to the given LibQTip tooltip.

- :new: **worldmap.lua** (`ns.utils.worldmap`) - A collection of utilities for the World Map.
  + Different `Enum.UIMapType` constants with the pattern: `ns.utils.handynotes.*_MAP_ID`
  + `:GetMapInfo(uiMapID)` &rarr; `mapInfo`: _UiMapDetails_  
    Return the map information for given map.
  + `:GetMapChildrenInfo(mapID, mapType, allDescendants)` &rarr; `mapChildrenInfos`: _UiMapDetails[]_  
    Get the map information for each child zone of given map.
  + `:GetMapInfoAtPosition(uiMapID, x, y, ignoreZoneMapPositionData)` &rarr; `mapInfo`: _UiMapDetails_  
    Return map information for any child map at given position on the map. _Note:_ The argument `ignoreZoneMapPositionData` is optional.
  + `:GetBestMapForPlayer()` &rarr; `uiMapID`: _number_  
    Returns the current uiMapID of the player's current location.
  + `:GetPlayerPosition()` &rarr; `playerMapPosition`: _Vector2DMixin|nil_  
    Returns the player's current map position.
  + `:IsMapTypeContinent(uiMapID)` &rarr; `isContinent`: _boolean_  
    Check whether the given map is a continent.
  + `:SetUserWaypointXY(uiMapID, posX, posY, setActive, chatNotifyOnError)` &rarr; `mapPoint`: _UiMapPoint|nil_  
    Set a user waypoint on given map at given position.
  + `:ClearUserWaypoint()`  
    Remove a previously set user waypoint.

----

## Disclaimer

> World of Warcraft© and Blizzard Entertainment© are all trademarks or registered trademarks of Blizzard Entertainment in the United States and/or other countries. These terms and all related materials, logos, and images are copyright © Blizzard Entertainment.
