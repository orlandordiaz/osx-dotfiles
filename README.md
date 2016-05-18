!/usr/bin/env bash

# Disable transparency in the menu bar and elsewhere on Yosemite
defaults write NSGlobalDomain AppleEnableMenuBarTransparency -bool false

# Disable press-and-hold for keys in favor of key repeat
defaults write NSGlobalDomain ApplePressAndHoldEnabled -bool false

# Set a blazingly fast keyboard repeat rate
defaults write NSGlobalDomain KeyRepeat -int 0



###############################################################################

# Set Desktop as the default location for new Finder windows
# For other paths, use `PfLo` and `file:///full/path/here/`

defaults write com.apple.finder NewWindowTarget -string "PfLo"
defaults write com.apple.finder NewWindowTargetPath -string "file://${HOME}"


# show ejectables, removables, servers
defaults write com.apple.sidebarlists systemitems -dict-add ShowEjectables -bool true
defaults write com.apple.sidebarlists systemitems -dict-add ShowRemovable -bool true
defaults write com.apple.sidebarlists systemitems -dict-add ShowServers -bool true
# do not show hard disks
defaults write com.apple.sidebarlists systemitems -dict-add ShowHardDisks -bool true


# Show icons for hard drives, servers, and removable media on the desktop
defaults write com.apple.finder ShowExternalHardDrivesOnDesktop -bool true
defaults write com.apple.finder ShowHardDrivesOnDesktop -bool true
defaults write com.apple.finder ShowMountedServersOnDesktop -bool true
defaults write com.apple.finder ShowRemovableMediaOnDesktop -bool true

# Finder: show hidden files by default
defaults write com.apple.finder AppleShowAllFiles -bool true

# Finder: show status bar
defaults write com.apple.finder ShowStatusBar -bool true

# Finder: show path bar
defaults write com.apple.finder ShowPathbar -bool true

# Display full POSIX path as Finder window title
defaults write com.apple.finder _FXShowPosixPathInTitle -bool true

# When performing a search, search the current folder by default
defaults write com.apple.finder FXDefaultSearchScope -string "SCcf"

# Disable the warning when changing a file extension
defaults write com.apple.finder FXEnableExtensionChangeWarning -bool false

# Disable disk image verification
defaults write com.apple.frameworks.diskimages skip-verify -bool true
defaults write com.apple.frameworks.diskimages skip-verify-locked -bool true
defaults write com.apple.frameworks.diskimages skip-verify-remote -bool true

# Use list view in all Finder windows by default
# Four-letter codes for the other view modes: `icnv`, `clmv`, `Flwv`
defaults write com.apple.finder FXPreferredViewStyle -string "Nlsv"

# Show the ~/Library folder
chflags nohidden ~/Library

# Show the /Volumes folder
sudo chflags nohidden /Volumes

# Expand the following File Info panes:
# “General”, “Open with”, and “Sharing & Permissions”
defaults write com.apple.finder FXInfoPanesExpanded -dict \
	General -bool true \
	OpenWith -bool true \
	Privileges -bool true

# Disable the warning before emptying the Trash
defaults write com.apple.finder WarnOnEmptyTrash -bool false

# Speed up Mission Control animations
defaults write com.apple.dock expose-animation-duration -float 0.2

# Top right screen corner → Desktop
defaults write com.apple.dock wvous-bl-corner -int 4
defaults write com.apple.dock wvous-bl-modifier -int 0

# Set home page to `about:blank` for faster loading
defaults write com.apple.Safari HomePage -string 'about:blank'

# Hide Safari’s sidebar in Top Sites
defaults write com.apple.Safari ShowSidebarInTopSites -bool false

defaults write com.apple.Safari DebugSnapshotsUpdatePolicy -int 2

#Doesn't work
defaults write com.apple.menuextra.battery ShowPercent -string “NO”
defaults write com.apple.menuextra.battery ShowTime -string “YES”

#Doesnt work
defaults write com.apple.Safari CanPromptForPushNotifications -bool false

# Expand save panel by default
defaults write NSGlobalDomain NSNavPanelExpandedStateForSaveMode -bool true
# Expand print panel by default
defaults write NSGlobalDomain PMPrintingExpandedStateForPrint -bool true

#NOT WORKING
sudo defaults write /Library/Preferences/com.apple.loginwindow AdminHostInfo HostName

###############################################################################
# iTunes
###############################################################################

# Make Command + F focus the search bar
defaults write com.apple.iTunes NSUserKeyEquivalents -dict-add “Target Search Field” “@F”

# Enable half-star ratings
defaults write com.apple.iTunes allow-half-stars -bool TRUE
###############################################################################
# Activity Monitor
###############################################################################

# Show the main window when launching Activity Monitor
defaults write com.apple.ActivityMonitor OpenMainWindow -bool true

# Show all processes in Activity Monitor
defaults write com.apple.ActivityMonitor ShowCategory -int 0

# Sort Activity Monitor results by CPU usage
defaults write com.apple.ActivityMonitor SortColumn -string "CPUUsage"
defaults write com.apple.ActivityMonitor SortDirection -int 0

##############################################################################
# OTHER
##############################################################################

# Opens a New window in the about:blank page
defaults write com.apple.Safari NewWindowBehavior -int 1


defaults write com.apple.Safari NewTabBehavior -int 1


# Enable Dock magnification
defaults write com.apple.dock magnification -bool true

# Menu bar: enable Keychain menu to easily lock system
defaults write com.apple.systemuiserver menuExtras -array "/Applications/Utilities/Keychain Access.app/Contents/Resources/Keychain.menu" "/System/Library/CoreServices/Menu Extras/TimeMachine.menu" "/System/Library/CoreServices/Menu Extras/Bluetooth.menu" "/System/Library/CoreServices/Menu Extras/AirPort.menu" "/System/Library/CoreServices/Menu Extras/Volume.menu" "/System/Library/CoreServices/Menu Extras/Battery.menu" "/System/Library/CoreServices/Menu Extras/Clock.menu"

# Disable beep sound effects
#defaults write com.apple.sound.beep.feedback -int 0
#defaults write com.apple.systemsound com.apple.sound.beep.volume -float 0
#defaults write com.apple.systemsound com.apple.sound.uiaudio.enabled -int 0

# Disable volume key feedback
defaults write NSGlobalDomain com.apple.sound.beep.feedback -float 0

# Change screenshot folder to  ~/screenshots
mkdir -p ~/screenshots
defaults write com.apple.screencapture location ~/screenshots

# Show scrollbars when scrolling; options: "Automatic, Always, WhenScrolling"
defaults write NSGlobalDomain AppleShowScrollBars -string "WhenScrolling"

# Disable dashboard
defaults write com.apple.dashboard mcx-disabled -boolean YES

# Set the dock icon size to 54 points
defaults write com.apple.dock tilesize -int 54

# Adds a Quit Finder menu item
defaults write com.apple.Finder QuitMenuItem -bool YES

# Send crash reports to the notification center
defaults write com.apple.CrashReporter UseUNC 1


