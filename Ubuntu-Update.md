# Update Ubuntu

## from Terminal

```sh
sudo apt update && sudo apt upgrade -y && flatpak update -y && sudo snap refresh
```

## add it as an alias

add the below line to `.bashrs` or `.zshrc`

```sh
alias update='sudo apt update && sudo apt upgrade -y && flatpak update -y && sudo snap refresh'
```
