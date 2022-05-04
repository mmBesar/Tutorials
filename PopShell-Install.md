# Install Pop Shell on other GNOME DEs

## Ubuntu and Zorin OS Core (Ubuntu Based Distros)

1. Install git and build dependencies

```sh
sudo apt install git node-typescript make
```

2. Clone the repository

```sh
git clone https://github.com/pop-os/shell.git
```

3. Open the new `shell` dir

```sh
cd shell
```

4. Install Pop Shell

```sh
make local-install
```

> NOTE:  
If you Get and error logout and login, then try the last two steps again