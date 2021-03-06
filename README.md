**Disclaimer**: 

*Pico-8 is not my own software or trademark, and is under copyright by Lexaloffle Games LLP. 
This repository is a creative transformation of content and serves no commercial purpose.*

# Man-Pages for the Pico8 Fantasy Console 

#### TL;DR? 

* Pre-formatted manpages, some installation scripts for said manpages, and a collection of
helper scripts for pulling up reference information about the Pico-8 Fantasy Console. 

* Repository TODO's can be found in `BUCKETLIST.md`. 

## What is Pico8? 

The Pico-8 (P8) Fantasy Console is a virutal machine and console emulator for hardware
that never existed, created by Joeseph White ([zep](https://twitter.com/lexaloffle)) in 2014. It comes with a unique colour 
palette and game engine running a Lua DSL familiar to programming on classic 8-bit 
computers and gaming consoles from the late 1970's. 

The fantasy game console has gained popularity after a number of free and open game
demonstrations (carts) made their way into the general gaming community (Celeste).

## Motivation 

Following convention for many long time Unix/Linux users, programming is often nicer
when the documentation is readily accessible. Common convention for *nix available 
binaries is well-formatted manual documents, or Manpages. 

Pico-8 already has documentation in a similar style, accessible [here](https://www.lexaloffle.com/pico-8.php?page=manual), 
however -- this isn't accessible as a manual standard most of us prefer, and there
are many aspects of the P8 API that are not concisely documented officially, but
have been elsewhere (see: [Pico-8 API reference](https://iiviigames.github.io/pico8-api/). 

# Contents 

## Standard Version

In `/p8_std`, you can find a collection of man-page documents that have already been 
formatted for compatibility on most *nix systems, along with installation script
`/p8_std/install.sh`, which, disclaimer, requires you have access to a compatible shell. 

The standard package only contains information found in the classic Pico-8 refernece 
manual ([above](https://www.lexaloffle.com/pico-8.php?page=manual)). It does not contain any helper scripts, and is a simple port.

To recompile the manpages from their source, check you have the required crate dependencies
in "Technical Notes", and call `build.sh`. 

#### Files: 

```
/p8_std
??????/src
??? ??????TBA
??????/pages
??? ??????TBA
??????/html
??? ??????TBA
??????build.sh 
??????install.sh 
```

## Extended Documents 

TBA 

```
Altruistic pico8 encyclopedia: 
https://www.pico-ate.com/

Fan-driven wiki: 
https://pico-8.fandom.com/wiki/Pico-8_Wikia
 
Game Development with PICO-8
by Dylan Bennet
https://mboffin.itch.io/gamedev-with-pico-8-issue1
```

# Technical Notes 

## Formats 

All of the manpages provided are written with `rust-cli/man`, a wrapper over the `roff-rs`
package, used for generating structured documentation in the rust programming language. 

The git repository for the wrapper can be found [here](https://github.com/rust-cli/man), and the docs can be found [here](https://docs.rs/man/0.3.0/man/). 

Documentation for `roff-rs` can be found via the [git repository](https://github.com/rust-cli/roff-rs). 


## Installation Scripts 


### Manual pages 

The installation scripts for the manpages, can store the data in two possible directories; 
`/usr/local/man/man1` is typically used for single user access, and `/usr/share/man/man1`
is more common for shared systems, or if the former does not work. 

You can specify a custome directory through modifying the `install.sh` script in the
package, by changing `$MAN_INSTALL_DIR`. 

### Helpers 

The helper scripts are written in C, then compiled and cached with `build.sh`, which is
called in the general installation script. If you want to build the files again, remove the
build directory `<pkg>/build`, or change `$BUILD_DIR` in `build.sh` to another folder name. 

# Special Thanks

None yet :) 
