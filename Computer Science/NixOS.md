---
tags:
  - linux
  - concept
---
NixOS is an [[Operating System]] based on the [[Nix]] [[Package Manager]].

# Cheat Sheet
## Build
```sh
# Build and activate the configuration
nixos-rebuild switch
# Rollback to the previous configuration build
nixos-rebuild switch --rollback
# Build and activate the configuration without making it the default
nixos-rebuild test
# Build the configuration and create a virtual machine to try it from
nixos-rebuild build-vm
./result/bin/run-\*-vm
```