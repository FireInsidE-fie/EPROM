
# Cheat Sheet
## General
```sh
# Remove unused packages from system
nix-collect-garbage
```
## Nix Shells
Nix Shells are **useful to try one or several packages without installing them permanently**.
You can also create nix shells inside of nix shells. Trippy!
```sh
# Create a temporary shell with specific packages to test them out
nix-shell -p cowsay lolcat
# Create a shell just to run a program
nix-shell -p cowsay --run "cowsay Nix"
# Use --pure to omit most environment variables from entering the shell
# This is useful for quick oneliners to be sure to run the right program
nix-shell -p cowsay --pure --run "cowsay Wow"
# Use -I to specify what to use as the source of package declarations
nix-shell -p git --run "git --version" --pure -I nixpkgs=https://github.com/NixOS/nixpkgs/tarball/2a601aafd...
```
## Nix Scripts
You can use the shebang `#!/usr/bin/env nix-shell` on a machine with a nix installation to **create a script that will install dependencies automatically on running**.
This allows a given script to run on any machine, with only one dependency: nix itself.
Here, we run three commands in succession, but first making sure that they are all installed, thanks to nix.
```
#!/usr/bin/env nix-shell
#! nix-shell -i bash --pure
#! nix-shell -p bash cacert curl jq python3Packages.xmljson
#! nix-shell -I nixpkgs=https://github.com/NixOS/nixpkgs/archive/2a601aafdc5605a5133a2ca506a34a3a73377247.tar.gz

curl https://github.com/NixOS/nixpkgs/releases.atom | xml2json | jq .
```
### Flags
- `-i` determines which interpreter to use to run the script for real
- `-p` lists packages that should be present in the interpreter's environment
- `--pure` excludes most of the environment before running
- `-I` sets the search path for packages; in the above case a specific commit of the nixpkgs repo
## Declarative Shell Environments
Creating *nix files* will allow you to **create a reproducible shell environment** that you can share with anyone who has nix installed.
Declarative shell environments allow you to:
- **Automatically run bash commands** during environment activation
- Automatically set **environment variables**
- Put the environment definition under **version control** and reproduce it on other machines
___
`nix-shell` by default searches for a `shell.nix` file in the current directory containing a nix expression, and runs it to create a shell.
# Resources
- [nix.dev](https://nix.dev/)