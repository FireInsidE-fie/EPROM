
# Cheat Sheet
## Nix Shells
Nix Shells are **useful to try one or several packages without installing them permanently**.
```sh
# Create a temporary shell with specific packages to test them out
nix-shell -p cowsay lolcat
# Create a shell just to run a program
nix-shell -p cowsay --run "cowsay Nix"
```