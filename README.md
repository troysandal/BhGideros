# Bowerhaus Gideros

This repository mimics the folder structure from [Bowerhaus library for Gideros](https://github.com/troysandal/BhWax/blob/master/README.md#folder-structure) using submodules from my own forks.  These forks are being updated for modern Gideros (iOS 18, Luau).  Intention is to get wax working on Lua 5.1 and Luau and Gideros Luau, then BhWax updated, along with all supporting tools, demos and examples, so it's not some half working project.  

An anti-goal for this project is to get wax working against Lua versions greater than 5.1, that's for someone else.

# Building
This project uses submodules so you need to init them after you first check out the project.
```
git clone git@github.com:troysandal/BhGideros.git
cd BhGideros
git submodule update --init --recursive
```

# To Do
This is a work in progress and not yet close to completion. The big things that need to be accompolished:

- [ ] wax - Lua 5.1 on macOS 15 / XCode 16
  - [ ] `lib/stdlib` compiling
  - [ ] Unit Tests Passing
  - [ ] `tools` ported
  - [ ] `examples` working
- [ ] wax (Gideros Luau)
  - [x] `tools` ported
  - [x] `examples` working
  - [x] setfenv/getfenv substitute
  - [ ] `lib/stdlib` (string.dump required - no go AFAICT)
  - [ ] unit tests passing under Gideros
- [ ] wax - Luau
  - [ ] Test against Luau HEAD
  - [ ] Incorporate Luau as sub-module 
- [ ] BhWax
  - [ ] examples working
  - [ ] Plugin/iOS 
    - [ ] hotwax modern xcode project
    - [ ] .giderosplugin

