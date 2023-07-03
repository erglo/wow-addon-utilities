# wow-addon-utilities

A collection of functions useful for World of Warcraft addon developers; feel free to use these in your own addon projects.  
Each LUA file of this repository is dedicated to a specific WoW topic and contains functions and constants related to that topic. See [Repository contents](#repository-contents) for an overview.

**Note:** _This is not an addon nor an Ace3 library (yet)!_
&nbsp;  

## Usage

There are multiple ways to include the utility files into your project. Here are some examples:

### 📦 Download and copy

1. Download the whole package or a single file of this repo.
2. Extract ZIP file or copy single file in a folder inside your project directory.
3. Add a reference to it in your addon's TOC file.
4. Use in your LUA files, eg. as follows:

    ```lua
    local AddonID, ns = ...
    -- 'ns.util' holds all utilities
    -- 'ns.util.achieve' holds all achievement related utilities, etc.
    ```

### 📝 Add to PKMETA file

Copy the below snippet to your `.pkmeta`/`pkmeta.yml` file:

```Yaml
externals:
  utils:  # path/to-your-utils
    url: https://github.com/erglo/wow-addon-utilities
    tag: latest
```

### 🔗 Use as a git submodule

```bash
# Links the submodule with folder "dir_name"
git submodule add https://github.com/erglo/wow-addon-utilities.git [dir_name]
# Copies all files from the submodule into "dir_name"
git submodule update --init
```

### ♻️ Clone this repository

```bash
git clone https://github.com/erglo/wow-addon-utilities.git
```

----

## Repository contents

The name of each file matches its topic:

- **achievements.lua** (`ns.util.achieve`)
  - `.GetWrappedAchievementInfo(achievementID, raw)` &rarr; _table|nil_  
    A key-value wrapper for [GetAchievementInfo()](https://wowpedia.fandom.com/wiki/API_GetAchievementInfo).
  - `.GetWrappedAchievementCriteriaInfo(achievementID, criteriaIndex, raw)` &rarr; _table|nil_  
    A key-value wrapper for [GetWrappedAchievementCriteriaInfo()](https://wowpedia.fandom.com/wiki/API_GetAchievementCriteriaInfo).
  - `.GetWrappedAchievementNumCriteria(achievementID, includeCompleted)` &rarr; _number, number|nil_  
    Retrieve the total and optionally the completed criteria number for given achievement.
  - `.IsAchievementCompleted(achievementID)` &rarr; _boolean_  
    Check whether given achievement has been completed.
  - `.IsAssetCriteriaCompleted(achievementID, assetID)` &rarr; _boolean_  
    Check if the criteria of given assetID for given achievementID has been completed.
  - `.GetAchievementCriteriaInfoList(achievementID)` &rarr; _array_  
    Retrieve all criteriaInfo for given achievement.
- **currencies.lua**
  - TODO - Add currency handler
- **worldmap.lua**
  - TODO - Add world map handler

----

## Disclaimer

> World of Warcraft© and Blizzard Entertainment© are all trademarks or registered trademarks of Blizzard Entertainment in the United States and/or other countries. These terms and all related materials, logos, and images are copyright © Blizzard Entertainment.
