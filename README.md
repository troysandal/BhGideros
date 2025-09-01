# Bowerhaus Wax for Gideros
## Goal and History
The goal of this project is to get the Wax Lua to Objective-C bridge working again in [Gideros](https://www.gideros.rocks/).  The impetus is to republish a 12 year old game I wrote using Gideros and Wax.  [Andy Bowerhaus](https://github.com/bowerhaus) started this effort, porting the original Wax to work under Gideros.  His work spanned multiple repositories that I have forked and included here in this parent project as submodules.  The biggest piece is Wax, originally written by [Corey Johnson](https://github.com/probablycorey/wax) but was taken over by [Alibaba](https://github.com/alibaba/wax). Alibaba ported wax to Arm64 and added proper Blocks support (THANK YOU) but hasn't committed anything in over 8 years.  

An anti-goal for this project is to get wax working against Lua versions greater than 5.1, that's for someone else. Some Luau changes should make this much easier, specifically the `wax_setEnvironment()` and and `wax_getEnvironment()` methods which add back the `lua_setfenv()/lua_getfenv()` support for userdata.  Still, Lua > 5.1 will not be tested.

## Repo Structure

This repository mimics the folder structure from [Bowerhaus library for Gideros](https://github.com/troysandal/BhWax/blob/master/README.md#folder-structure) using submodules from my own forks.  These forks are being updated for modern Gideros (iOS 18, Luau).  Intention is to get wax working on Lua 5.1 and Luau and Gideros Luau, then BhWax updated, along with all supporting tools, demos and examples, so it's not some half working project.  


## Building
This project uses submodules so you need to init them after you first check out the project.
```
git clone git@github.com:troysandal/BhGideros.git
cd BhGideros
git submodule update --init --recursive
```

## Status
**2025-09-01** - lua_setfenv() and lua_getfenv() replacements appear to be working against the BhWaxDemo examples. At this point I would say the project is ready for testing.

### Task List
- [ ] wax - Lua 5.1 on macOS 15 / XCode 16
  - [ ] `tools`
  - [ ] `examples`
  - [ ] `lib/stdlib`
  - [ ] Wax Cocoa Pod
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
- [ ] wax - Luau
  - [ ] Instruction on how to incorporate Luau
  - [ ] `tools`
  - [ ] `examples` 
  - [ ] `lib/stdlib`
    - Requires `string.dump` which was removed by Luau and is a ton of work to add back.  Users can just `require` these files in their project.
  - [ ] Wax Cocoa Pod
  - [ ] WAX_TEST (As Gideros Plugin)
  - [ ] WAX_REPL
  - [x] setfenv/getfenv substitute
- [ ] BhWax
  - [ ] WaxDemoXxx working
  - [ ] Plugin/iOS 
    - [ ] hotwax modern xcode project
    - [ ] Modern .giderosplugin

