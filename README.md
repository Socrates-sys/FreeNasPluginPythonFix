# FreeNAS Plugins Python Fix

First of all: sorry for my bad english.

##  If you get an error "Python is not detected" in a FreeNAS plugin you may follow this steps for fix it. In my case i was getting error from qBittorrent Web UI (#webui) plugin in FreeNAS when i was wanna install "search plugins" for qBittorrent.

### 1- Click jails and then click 3 dots near of plugin and click shell
![1](https://user-images.githubusercontent.com/59617701/71914905-a95ed100-318b-11ea-8fd6-b1a380fa809f.png)
### 2- Type in shell:
```bash
  cd /usr/local/bin/
  ln -s python3.6 python3
  ln -s python3 python
  ls -l | grep python
```
####  and check can you see "python -> python3" on screen
![2](https://user-images.githubusercontent.com/59617701/71914906-a95ed100-318b-11ea-8f67-d19b5d3fde75.png)
### 3- Go to iocage/jails/qbittorrent/root/etc folder and open **rc.local** with a text editor
![3](https://user-images.githubusercontent.com/59617701/71914907-a95ed100-318b-11ea-99c9-4eba0862e1dc.png)
### 4- Add   export PATH="$PATH:/usr/local/bin"
![4](https://user-images.githubusercontent.com/59617701/71914908-a9f76780-318b-11ea-99c5-0e81ac82e43d.png)
### 5- Restart plugin
![5](https://user-images.githubusercontent.com/59617701/71914910-a9f76780-318b-11ea-8956-d71b5a33a6df.png)
### 6- Open qbittorent webui. type "admin" in username input field, "adminadmin" password input field
![6](https://user-images.githubusercontent.com/59617701/71915267-70732c00-318c-11ea-9d4f-c3ede4b97444.png)
### 7- Click search and then search plugins
![7](https://user-images.githubusercontent.com/59617701/71915268-70732c00-318c-11ea-8454-b5a43d7e88a6.png)
### 8- Check for updates after u should see search plugins
![8](https://user-images.githubusercontent.com/59617701/71915269-70732c00-318c-11ea-9d25-a17ddc958381.png)
### 9- it took my days to find solution. if you want, you can buy a coffee to me. Thanks
