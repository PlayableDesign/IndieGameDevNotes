# Deployment with Samsung Secure Folders

* Unity 2020, probably all other versions also

When deploying a game direct to a Samsung phone via USB connection, it would fail as a "timeout error". When trying to install from Google Play, the phone would report that the app is already installed, although I had uninstalled it and could find no evidence of the app on the phone.

Exploring every folder on the phone for any leftover artifact nothing is found. Checking Samsung's Secure Folder (feature that stores apps and files in a secure, encrypted area) the game was discovered to have been installed here despite never specifying this option.

Resolved by manually uninstalling from Secure Folder, disabling the Secure Folder feature in settings on test devices.
