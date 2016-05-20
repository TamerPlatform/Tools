# AndroidTamer Repository in Debian 8

### How to configure

```bash
$ echo "deb https://repo.androidtamer.com Tamer4 main" | sudo tee  /etc/apt/sources.list.d/repo_androidtamer_com.list
```

### Adding GPG Key

```bash
wget -qO - https://androidtamer.com/repo.gpg.key | sudo apt-key add -
```

### Enable HTTPS Debian repositories

```bash
sudo apt-get install apt-transport-https
```

### How to install pacakges

```
$ sudo apt-get update
$ sudo apt-get install <package name>
```

### GUI

![Synaptic screen](/images/synaptic.jpg)


### List of Available packages

[https://repo.androidtamer.com/packagelist.html](https://repo.androidtamer.com/packagelist.html)