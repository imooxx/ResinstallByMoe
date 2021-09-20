# Note

## MacOS
### Uncheck "Reopen windows when logging back in" by defaults
```
defaults write com.apple.loginwindow TALLogoutSavesState -bool FALSE
```

### Diasble other account
```
defaults write com.apple.loginwindow SHOWOTHERUSERS_MANAGED -bool FALSE
```

### Disable system update
```
defaults write com.apple.systempreferences AttentionPrefBundleIDs 0
```

### Disable App Store Update Notification
```
sudo defaults write /Library/Preferences/com.apple.AppStore.plist DisableSoftwareUpdateNotifications -bool TRUE
```

### Delete system file
```
# Disbale SIP (command + r)
csrutil disable

# Mount '/' as write
sudo mount -uw /

# Do something
sudo cd "/Volumes/$(ls -1 /Volumes|head -n1)"
sudo rm -rf /System/Applications/TV.app
sudo rm -rf /System/Applications/News.app
sudo rm -rf /System/Applications/Home.app
sudo rm -rf /System/Applications/Books.app
sudo rm -rf /System/Applications/Chess.app
sudo rm -rf /System/Applications/Podcasts.app
sudo rm -rf /System/Applications/Stocks.app
sudo rm -rf /System/Applications/Music.app

# Enable SIP
csrutil enable
```

# Modify user name and folder
- Create a user as Administrator, like "temp".
- Login "temp".
- Change user name and folder.
- Disable SIP.
- Use `sudo mv <OldFolder> <NewFolder>` to rename folder.
- Enable SIP.
- Login.
- Delete user "temp".


# NET Reinstall code
```
bash <(wget --no-check-certificate -qO- 'https://raw.githubusercontent.com/imooxx/Note/master/InstallNET.sh') -d 10 -v 64 -a
```
```
MoeClub.org
```
#New Reinstall code
Code Owner: https://github.com/MoeClub/Note
```
1. 新增对 `Oracle AMD`，`Oracle ARM`全面支持. 可支持从 `Ubuntu`, `Oracle Linux` 等系统网络重装. 
2. 更新 `dd` 镜像的基础系统版本.
3. 移除对外部 `wget `的依赖.
4. 新增 `-port` 参数, 可更改默认SSH端口.
5. 更新 内置的网络参数计算 逻辑.
6. 更新 `grub` 配置文件定位逻辑, 可支持任意引导`grub`的系统.
 以下系统已通过测试(其他自测):
`Debian`: `9`, `10`, `11`;
`Ubuntu`: `18.04`, `20.04`;
`CentOS`: `6.10`;
示例:
bash <(wget --no-check-certificate -qO- 'https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh') -d 10 -v 64 -p "自定义root密码" -port "自定义ssh端口"
```
