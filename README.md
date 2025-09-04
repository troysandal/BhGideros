# Bowerhaus Wax for Gideros
## Goal and History
The goal of this project is to get the [Wax](https://github.com/troysandal/wax) Lua to Objective-C bridge working again in [Gideros](https://www.gideros.rocks/).  The impetus is to republish a 12 year old game I wrote using Gideros and Wax.  [Andy Bowerhaus](https://github.com/bowerhaus) did the original port and his work spanned multiple repositories that I have forked and included here in this parent project as submodules.  The biggest piece is Wax, originally written by [Corey Johnson](https://github.com/probablycorey/wax) but was taken over by [Alibaba](https://github.com/alibaba/wax). Alibaba ported wax to Arm64 and added proper Blocks support (THANK YOU) but hasn't committed anything in over 8 years.  My intention is to get wax working on Lua 5.1 and Gideros Luau, along with all supporting tools, demos and examples, so it's not some half working project.  

An anti-goal for this project is to get wax working against Lua versions greater than 5.1, or Roblox Luau, that's for someone else. However, some changes I made, specifically the `wax_setEnvironment()` and and `wax_getEnvironment()` methods which add back the `lua_setfenv()/lua_getfenv()`, should make it easier.  

## Repo Structure

This repository enforces the folder structure originaly defined by Bowerhaus.  It uses submodules from my own forks to keep things structured.  That does means you need to understand submodules.  

| Folder | Description |
| :----- | :---------- |
| BhGideros/Bowerhaus | Bowerhaus libraries |
| BhGideros/Bowerhaus/BhHelpers | Hlper/utility functions. |
| BhGideros/Bowerhaus/BhWax | Gideros plugin and demo project |
| BhGideros/Gideros | Miscellaneous Gideros classes, including SceneManager. |
| BhGideros/Misc | Miscellaneous classes, such as GTween and Easing. |
| BhGideros/wax | Gideros Luau compatible wax |

## Fetching & Building
1. This project uses submodules so you need to init them after you first check out the project.
``` sh
# Fetch repo and submodules
git clone git@github.com:troysandal/BhGideros.git
cd BhGideros
git submodule update --init --recursive
```
2. Build the Gideros pluging and player + wax
```sh
# Build wax plugin and player
cd Bowerhaus/BhWax/Plugin
./build.sh
./install.sh

cd ../Player
./build.sh
```
3. Follow [Player README](Bowerhaus/BhWax/Player/README.md) to get it building and running
3. Open [BhWaxDemo](Bowerhaus/BhWax/Demo/BhWaxDemo.gproj) in Gideros Studio and play with the examples.

## Status
**2025-09-03** - [Gideros plugin](https://github.com/troysandal/BhWax) landed.

**2025-09-01** - lua_setfenv() and lua_getfenv() replacements appear to be working against the BhWaxDemo examples. At this point I would say the project is ready for testing.

### Task List
- [ ] wax - Lua 5.1 on macOS 15 / XCode 16
  - [x] `tools`
  - [x] `examples`
  - [ ] `lib/stdlib`
  - [x] Wax Cocoa Pod
  - [ ] WAX_TEST
  - [ ] WAX_REPL
- [ ] wax (Gideros Luau)
  - [ ] Bowerhaus Changes Back Ported
  - [x] `tools`
  - [x] `examples` 
  - [ ] `lib/stdlib`
    - Requires `string.dump` which was removed by Luau and is a ton of work to add back.  Users can just `require` these files in their project.
  - [ ] Wax Cocoa Pod
  - [ ] WAX_TEST (As Gideros Plugin)
  - [ ] WAX_REPL
  - [x] setfenv/getfenv substitute
- [x] BhWax
  - [x] WaxDemoXxx working
  - [x] Plugin/iOS 
    - [x] hotwax modern xcode project
    - [x] Modern .giderosplugin

