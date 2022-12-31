### Select file/folder with single click (for shift click or alt click selections)
1. System Settings (app)
2. Workspace Behaviour
3. General Behavior
4. Clicking files or folders > Selects them


### SSH with Fish
- In the url/path bar
    - fish://user@ipaddress
    - Stream media from another PC..

### Custom Right Click Menu
- kf5-config --path services
- vim $HOME/.local/share/kservices5/ServiceMenus/action.desktop
- Example .desktop (resources for % entry keys)
```
[Desktop Entry]
Type=Service
Icon=edit-copy
X-KDE-ServiceTypes=KonqPopupMenu/Plugin
MimeType=directories;all/all;
Actions=cppath;
Encoding=UTF-8
Terminal=false

[Desktop Action cppath]
Name=Copy Path
Icon=edit-copy
Exec=echo "%f" | xclip -selection c
Terminal=false
```
- Can't Copy Folder Path
    - Settings > Configure Dolphin > Services > Check Copy Path
    - Right click folder > Actions > Copy Path

### Rotate Images, convert, etc. (Right click menu)
- https://github.com/caco3/kim5

### Resources
- https://specifications.freedesktop.org/desktop-entry-spec/latest/ar01s06.html
