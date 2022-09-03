# WW Macbook Setup

## Base Installation

- First install [Homebrew](https://brew.sh/). This enables easier installation of the rest of the apps.

## Keyboard

- Install [karabiner](karabiner-elements.pqrs.org) and download the Karibiner config from this repo. Load the config. This will enable most of the keyboard configs in [Capsy](https://github.com/wayanlw/Capsy)

## Terminal

- In apple by default zsh is the main shell.
  - install [iterm2](https://iterm2.com/) and change the keymappings via  `Preferences > profile > keys > keymapping > presets > natural keys`
  - Install [ohmyzsh](https://ohmyz.sh)
- install Tmux and copy the [.tmux.conf](https://github.com/wayanlw/dotfiles/blob/master/.tmux.conf) to the home folder.
- install vim, install [vimplug](https://github.com/junegunn/vim-plug) and copy the [.vimrc](https://github.com/wayanlw/dotfiles/blob/master/.vimrc)

## Other Software

- Install [brave](http://brave.com) browser and configure it for maximum privacy.
- Install [vscode](https://code.visualstudio.com/)
- Install [rectangle](https://rectangleapp.com/). This enables managing windows easily with a keyboard, similar to windows. Assign `command+shift+wer` for full screen, left-split and right-split.
- Install [alt-tab](https://alt-tab-macos.netlify.app/).
  - This provides windows-like alt-tab functionality. ie. If there are different windows of the same app, it shows them separately.
  - Change the view mode to windows 10
  - Remap the keyboard shortcut to `cmd+tab` and `cmd + ``
- Install [cheatsheet](https://www.mediaatelier.com/CheatSheet/). This enables the user to view and access all keyboard shortcuts for an app by holding the `Cmd` key.
- Install skim (pdf reader) - Easier annotation
- Install [Maccy](https://github.com/p0deje/Maccy). This is a clipboard manager with history. Enable automatic pasting when selected, instead of copying the selection to the clipboard.
- Install [appcleaner](https://freemacsoft.net/appcleaner/) - Deletes config files etc. installed with an app

## Menubar Apps

- Install [dozer](https://github.com/Mortennn/Dozer). This optimizes the menu bar space. [ [Bartender](https://www.macbartender.com) is a better app than this. However, it is a paid app]
- Install [stats](https://github.com/exelban/stats) - Menu bar performance stats monitor. [ [istatmenu](https://bjango.com/mac/istatmenus/) is a better alternative. But it is a paid software.]
- Install [clean-me](https://github.com/Kevin-De-Koninck/Clean-Me). This cleans the caches etc. which are temp files. Can clean about 1.5 GB
- Install [Latest](https://github.com/mangerlahn/latest). This can check for updates for all installed apps at once.
- Install [keepassxc](https://keepassxc.org/download/#mac). Best password manager.
- Install [swish](https://highlyopinionated.co/swish/). It is a paid app. But one of the best window managers for mac. Utilizes gestures to manage the windows. Alternatives would be [penc](https://deniz.co/penc/).


## Configurations

- Dock Settings
  - Move the Dock to the left
  - Adjust the dock autohide timing  and other settings with [Tinker Tool](http://www.bresink.com/osx/0TinkerTool/download.php)
- Trackpad configurations
  - Enable three-finger drag (in accessibility settings)
  - Increase tracking speed
  - Enable tap to click (trackpad settings)
- Activate hot-corners
  - `Desktop and screensavers > screen saver > hot corner`
  - If you only want to activate it when a modifier is pressed, in the dropdown menu select the action while holding the modifier. [details](https://youtu.be/9Lz7jliEvGg?t=2011)
- Accessibility > reduce motion
- Enable battery percentage in `System Preferences > Dock and Menu Bar > Battery > Enable Battery Percentage`
- Enable night shift in display
- Disable truetone in display settings
- Change to Scaled > More space (This makes text smaller, but significantly improves productivity due to more space.
Right-click on the desktop and enable stacks
- Keyboard
  - Enable key repeating. Before this config, when a key is held, special characters instead of key repeat. Can use the tinker tool or command-line method](https://www.howtogeek.com/267463/how-to-enable-key-repeating-in-macos/) ie. `defaults write -g ApplePressAndHoldEnabled -bool false`. To revert to default do `defaults write -g ApplePressAndHoldEnabled -bool true`
  - Shorten the `delay until repeat keys`. This increases the repetition speed.
  - Enable `F1`, and `F2` keys without pressing the `fn` keys (in Preferences > keyboard). By default, the extra functionality such as brightness, and volume are activated with Function keys.
  - Swap the function and Control keys. If you are coming from windows, this would significantly help. `Keyboard > Modifier keys > Swap Fn and Ctrl keys`
  - Preferences > keyboard > shortcuts > enable "use keyboard navigation to move focus between controls". This enables traversing through controls easily with the tab key.


- [Tinker Tool](http://www.bresink.com/osx/TinkerTool.html)
  - Finder > Show hidden files
  - Dock options > Disable animations and delay
  - Launchpad > disable all
  - General
    - Support key repeat (This is mentioned above in the keyboard section)
      - this does `defaults write -g ApplePressAndHoldEnabled -bool false`
      - To revert from command line `defaults write -g ApplePressAndHoldEnabled -bool true`
        - [source](https://www.howtogeek.com/267463/how-to-enable-key-repeating-in-macos/)
    - Turn off `animate opening windows`
  - Applications > Don't ask for backup disks. This stops mac from asking whether it needs to use the plugged-in drive as a time machine backup, every time you plug in an external drive.

- [Terminal Commands](https://www.youtube.com/watch?v=9Lz7jliEvGg&t=1481s)
  - Screenshot format (can change JPG to PNG, TIFF, PDF)
    - `defaults write com.apple.screen capture type JPG`
  - Mac App Store update check frequency (change 7 to any number of days)
    - `defaults write com.apple.SoftwareUpdate ScheduleFrequency -int 7`
  - Disable the character accent menu (revert by changing 'false' to 'true')
    - `defaults write -g ApplePressAndHoldEnabled -bool false`
  - Keep Mac running (end by closing the Terminal window or pressing Control+C)
    - `caffeinate`
  - Expand print dialogue by default (revert by changing TRUE to FALSE)
    - `defaults write -g PMPrintingExpandedStateForPrint -bool TRUE`
  - Re-enable classic Mac boot chime (restore default by changing %00 to %01)
    - `sudo nvram StartupMute=%00`
  - Add dock spaces (remove by dragging space off dock like normal)
    - `defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="spacer-tile";}'; killall Dock`
  - Dock transition/reveal delay
    - `defaults write com.apple.dock autohide-delay -float 0; killall Dock` (reduces delay)
    - `defaults write com.apple.dock autohide-time-modifier -float 0; killall Dock` (removes animation)`

## Finder

- Make folders come on top ( Preferences >> advanced )
- Show all file name extensions
- Show hidden files in finder - `SHIFT + COMMAND + PERIOD `
- Status bar
  - Finder > View > Show Path Bar
  - Finder > Go > Hold down option > Library (you can now add to Sidebar from "File")
  - Finder > View > Show Status Bar
  - Toolbar
  - Change the icons in the toolbar (by right-clicking)
  - Add required folders and apps to the toolbar
- Preferences
  - Finder > Preferences > General > Uncheck "Open folders in tabs instead of new windows"
  - Finder > Preferences > General > New Finder windows show "Documents" (instead of "Recents")
  - Finder > Preferences > Tags > Uncheck those you don't use
  - Finder > Preferences > Advanced > Search the Current Folder when performing a search
  - Finder > Preferences > Advanced > Show folders at the top
- File Operations
  - Drag and drop copying --> copy to the parent folder by dropping into the info columns in the detailed view
  - Click on the expand icon of a folder with `OPTION` to expand old child folders
  - `CMD`+`OPTION` to create a folder alias
  - `OPTION`+drag to quickly copy a file or folder
  - `OPTION`+click to expand all child folders
  - `CMD`+`i` while selecting a file to change the default app to open with
  - Open image > Markup > Edit size and you can change the size of the file (proportions stay the same)
  - Select multiple images > Right click > Quick actions > Create PDF (you can move the pages around)
  - Open PDF > File > Export as PNG or JPEG
  - Keynote presentations can be exported as a PPT file, Numbers can be exported as Excel files, and Pages as Word Doc files
  - Multi-renaming files
  - Cut pasting > Copy and then `OPTION` + `COMMAND` + `v`
- Accessing Finder panels faster
  - Shift+Command+a > Applications
  - Shift+Command+o > Documents
  - Shift+Command+p > show file preview on the right side
  - Other
- In multi-column view, change column width whilst holding `OPTION` to resize all columns equally

## Other Tips

- Drag windows under the current windows while holding the `COMMAND` key > then the below window will not come to the top. It will move behind the active window
- Show a custom message on the lock screen. eg. Have your mobile number or email in here. So if you left your mac somewhere and if a good samaritan finds it, they can inform you.
  - Preferences > security and privacy > (unlock admin) > set lock message
- Cancel Dialog boxes with `COMMAND + PERIOD`
- Use "Photo Booth" to check how you look before zoom meetings. Alternative is [handmirror](https://handmirror.app/)
- Printing
  - Go to printers and drag the required printer to the desktop. Then drag the document to the printer, and it will print (without any other dialog boxes)
  - When using the QuickLook, hold the `SPACE` key. When you let go of it, QuickLook will close automatically. Quite useful if looking at multiple files quickly.
  - When pasting text paste with `Shift+Option+Command+V` to paste as text
- Menu bar (System tray)
  - Hold the `COMMAND` key and drag and drop menu bar icons outside to remove them. Can only be done for some icons.
- Text Editing
  - Halfway typing a word and then pressing `F5` > shows a drop-down of word auto-completion
- Force quitting apps
  - Force quit option 1 - Use Activity Monitor
  - Force quit option 2 - CMD+OPTION+ESC
  - Force quit option 3 - Right click on the app in the dock and hold down OPTION

## Screenshots

- Native Screenshot
  - `Shift+CMD+3` > Capture Full Screen
  - `Shift+CMD+4` > picture of a selection
  - `Shift+CMD+4` and then press space >  picture of a window
  - `Shift+CMD+4` and then press and hold space >  move the selection
  - `Shift+CMD+4` and then press and hold space and move and release space and resize (if holding `OPTION` resize from the middle) >> different option combinations with `OPTION` and `COMMAND`
  - `Shift+CMD+4` and then space and then click whilst holding `OPTION` > screenshot without the formatting and shadows
  - `Shift+CTRL+CMD+4` > don't save the screenshot to the folder. but copy to clipboard.
  - `Shift+CMD+5`
- Other screenshot software
  - [Skitch](https://apps.apple.com/us/app/skitch-snap-mark-up-share/id425955336?mt=12)


## Dock

- Right-click on the vertical line within the deck to quickly get to Dock Preferences
- Hold down "Shift" and drag the vertical line to move the Dock
- In dock preferences, untick `show recent apps in the dock`
- Enable auto-hide > But change the animation and delay settings using the tinker tool
- Opt+Cmd+D - Toggles dock show/hide
- Add AirDrop to Dock (a) go to Finder, (b) press Shift+Cmd+G, (c) paste this: /System/Library/CoreServices/Finder.app/Contents/Applications/ (d) drag AirDrop icon into Dock


# Applications List

Do a web search with <application name> mac app to find details. Almost all of the apps are available in homebrew. So simply search for the app with `brew search <app name>` and install with `brew install <app name>`

- Archiving tools
  - unarchiver
  - kaka
  - betterzip (PAID) > this allows looking at the archives using QuickLook. (enable in the app settings)

- video player
  - iina

- RSS Raadrs
  - [Net News Wire](https://netnewswire.com/)

- Pdf reader
  - Skim

- Create apps from any website with their favicon as the icon
  - Fluid - Create apps from any website.

- Media downloader
  - Downie (PAID)

- Conky like desktop widget
  - [uebersicht](https://tracesof.net/uebersicht/). Get widgets from [here](https://tracesof.net/uebersicht-widgets/)


- Status Bar
  - [Dozer](https://github.com/Mortennn/Dozer/)
    - alternative: [Hidden Bar](https://github.com/dwarvesf/hidden)
    - alternative: Bartender (PAID)
  - Stats - display system stats
    - alternative: istat menus

- Launcher
  - [Raycast](https://www.raycast.com/)
    - better paid alternative: [Alfred](https://www.alfredapp.com/) (PAID)

- Drop files and folders
  - [Drop zone (Paid)](https://aptonic.com/)

- Clean unwanted apps
  - [clean-me](https://github.com/Kevin-De-Koninck/Clean-Me)
  - [App Cleaner](https://freemacsoft.net/appcleaner/)
  - [onyx](https://www.titanium-software.fr/en/onyx.html)

- Mouse tools
  - mos

- Disk Usage Monitor
  - [disk inventory x](http://www.derlien.com/)

- OCR
  - Text sniper(PAID)

- Window Management
  - Rectangle (Free) - https://rectangleapp.com/
  - [penc](https://deniz.co/penc/)
  - Spectacle (not maintained),
  - magnet (PAID)
  - Moon (Paid) - https://manytricks.com/moom/
  - [swish](https://highlyopinionated.co/swish/)

- Tiling Window Manager
  - Amethyst
  - Yabai with Shkd —> video josh Medeski - blazing fast window management
  - Space launcher for Mac OS. —> same video as above

- Mac customization (Eg. improve launcher bar. Refer https://www.youtube.com/watch?v=h2xoRkzjQoc)
  - Tinker tool - https://www.bresink.com/osx/TinkerTool.html

- Clipboard Manager
  - [Maccy (Free)](https://github.com/p0deje/Maccy)
  - alternative -[Copy Clip (Free)](https://apps.apple.com/us/app/copyclip-clipboard-history/id595191960?mt=12)

- Torrent Download
  - Transmission

- Keep the mac awake
  - Amphetamine

- Display the app's shortcuts
  - [Cheat Sheet](https://www.mediaatelier.com/CheatSheet/)

- Local audio recorder that lets you save audio your mic heard in the past.
  - [Backtrack](https://www.backtrack.team/)

- App updaters
  - [Latest](https://github.com/mangerlahn/latest) - checks for updates for all installed apps at once
  - MacUpdater (PAID)

- Commandline like calc
  - Numi - https://numi.app/

- Windows like alt-tab
  - alttab - https://alt-tab-macos.netlify.app/

- multi-browser tool
  - Enables opening links in selected browsers

- Workspaces management - Enables opening a predetermined list of applications
  - [bunch](https://bunchapp.co/)
  - Workspace (PAID) - Faster workspace creation
  - Workspaces Pro (PAID)- Faster workspace creation

- Vim-like access - Access GUI elements with keyboard]
  - [Vim Easy motions for mac](https://github.com/dwarvesf/VimMotionApp)

- Type in your iPhone using mac
  - [Keypad - Bluetooth keyboard](https://apps.apple.com/in/app/keypad-bluetooth-keyboard/id1491684442)

- Run Windows apps like native apps
  - Parallels (PAID)



---
# Paid List that is worthwhile to consider

- Dropzone
- Workspace - Faster workspace creation OR Workspaces Pro - Faster workspace creation
- Text sniper
- Parallels
- Alfred powerpack
- swish

---

# Full List of Installed Apps

- Alfred 5.app
- AltTab.app
- App Cleaner 7.app
- AppCleaner.app
- Brave Browser.app
- Bunch.app
- Caffeine.app
- CheatSheet.app
- Clean Me.app
- Disk Inventory X.app
- Dozer.app
- Dropzone 4.app
- Fluid.app
- IINA.app
- Kap.app
- Karabiner-Elements.app
- KeePassXC.app
- Keynote.app
- Latest.app
- Maccy.app
- Malwarebytes.app
- Mos.app
- Numi.app
- OnyX.app
- Penc.app
- ProtonVPN.app
- Raycast.app
- Rectangle.app
- Skim.app
- Skitch.app
- Slidepad.app
- Stats.app
- Swish.app
- TextMate.app
- TextSniper.app
- TinkerTool.app
- Visual Studio Code.app
- WorkspacePro.app
- Workspaces.app
- iTerm.app
- xbar.app
- zoom.us.app

## References
- [awesome mac apps](https://github.com/jaywcjlove/awesome-mac)
- [Mac apps list](https://github.com/serhii-londar/open-source-mac-os-apps)
- [video by Jeffsu](https://www.youtube.com/watch?v=-xXc7qeiC8I)
- [150+ Mac Tips and Tricks - by Snazzy Labs]https://www.youtube.com/watch?v=9Lz7jliEvGg&t=69s
- [digital inspiration](https://www.labnol.org/software/essential-mac-utilities/9479/)
- https://www.youtube.com/watch?v=dPddVTRBScw
- https://www.youtube.com/watch?v=o2RRDS2tIoY
- https://www.youtube.com/watch?v=0DSWeFLgMMI
- https://www.youtube.com/watch?v=oKXApo3nuHY


