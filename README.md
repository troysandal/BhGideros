# Bowerhaus Gideros

This repository mimics the folder structure for the [Bowerhaus library for Gideros](https://github.com/troysandal/BhWax/blob/master/README.md#folder-structure) using submodule from my own forks.  These forks are being updated for modern Gideros (iOS 18, Luau).  

An anti-goal for this project is to get wax working against Lua versions greater than 5.1, that's for someone else.

# Building
This project uses sub-modules so you need to init them after you first check out the project.
```
git clone git@github.com:troysandal/BhGideros.git
cd BhGideros
git submodule update --init --recursive
```

# To Do
This is a total work in progress and not yet close to completion. The big things that need to be accompolished:

- [ ] wax (Lua 5.1)
  - [ ] `lib/stdlib` compiling
  - [ ] Unit Tests Passing
  - [ ] `tools` ported
  - [ ] `examples` working
- [ ] wax (Gideros Luau)
  - [ ] `lib/stdlib` compiling
  - [ ] unit tests passing as Gideros pluging
- [ ] BhWax
  - [ ] examples working
  - [ ] Plugin/iOS 
    - [ ] hotwax modern xcode project
    - [ ] .giderosplugin

