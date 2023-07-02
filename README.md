# wow-addon-utilities

A collection of functions useful for World of Warcraft addon developers; feel free to use these in your addon projects.  
Each file is dedicated to a specific topic. See [Repository contents](#repository-contents) for an overview.

**Note:** _This is not an addon nor an Ace3 library (yet)!_
&nbsp;  

## Usage

There are multiple ways to include the utility files into your project. Here are some examples:

### 📦 Download and copy

1. Download the whole package or a single file of this repo.
2. Extract ZIP file or copy single file in a folder inside your project directory.
3. Add a reference to it in the addon's TOC file.
4. Use in your LUA files, eg. as follows:

    ```lua
    local AddonID, ns = ...
    -- 'ns.util' holds all utilities
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

The contents of each file match their names:

- `achievements.lua`
- `currencies.lua`

----

## Disclaimer

> World of Warcraft© and Blizzard Entertainment© are all trademarks or registered trademarks of Blizzard Entertainment in the United States and/or other countries. These terms and all related materials, logos, and images are copyright © Blizzard Entertainment.
