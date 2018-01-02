# Clarity SRS (Simple Repository System)

Clarity SRS (Simple Repository System) works somewhat like a Cydia APT Repository with some changes to the layout and mapping of files.

## Getting Started

To create your own Clarity Repository you'll need to download this GitHub Repository to get started.

### Prerequisites

You'll need software to create tar.gz files and know where your tweaks will go to.

```
Icon Masks:
Folder Structure: /System/Library/PrivateFrameworks/MobileIcons.frameworks
The Following Files are REQUIRED for Icon Masks:
Name: AppIconMask@2x.png
Size: (120px x 120px)
Name: AppIconMask@2x~ipad.png
Size: (152px x 152px)
Name: AppIconMask@2x~iphone.png
Size: (120px x 120px)
Name: AppIconMask@3x.png
Size: (180px x 180px)
Name: AppIconMask@3x~ipad.png
Size: (180px x 180px)
Name: AppIconMask@3x~iphone.png
Size: (180px x 180px)
Name: FolderMask@3x.png
Size: (908px x 980px)
Name: GameAppIconMask@2x.png
Size: (84px x 84px)
Name: GameAppIconMask@3x.png
Size: (180px x 180px)
Name: NotificationAppIconMask@2x.png
Size: (40px x 40px)
Name: NotificationAppIconMask@3x.png
Size: (60px x 60px)
Name: SpotlightAppIconMask@2x.png
Size: (80px x 80px)
Name: SpotlightAppIconMask@3x.png
Size: (120px x 120px)
Name: TableIconMask@2x.png
Size: (58px x 58px)
Name: TableIconMask@3x.png
Size: (87px x 87px)
```

### PACKAGE LISTING

To display a package in Clarity you need to layout your PACKAGES file like this

```
Package: sh.joseph.clarity.custom_carrier
Name: Custom Carrier
Version: 1.0
Architecture: iphoneos-arm
Description: This package allows you to set a custom carrier
Depiction: https://srs.joseph.sh/packages/custom_carrier.html
Homepage: http://srs.joseph.sh
Maintainer: Joseph Shenton <joe@joseph.sh>
Author: Joseph Shenton <joe@joseph.sh>
Section: Tweaks
Location: custom_carrier.tar.gz

Package: sh.joseph.clarity.lotus_icon_mask
Name: Lotus Icon Mask
Version: 1.0
Architecture: iphoneos-arm
Description: This package allows you to have the same icon mask in the Lotus theme.
Depiction: https://srs.joseph.sh/packages/lotus_icon_mask.html
Homepage: http://srs.joseph.sh
Maintainer: Joseph Shenton <joe@joseph.sh>
Author: Joseph Shenton <joe@joseph.sh>
Section: Themes
Location: lotus_icon_mask.tar.gz
```

If you do not layout your PACKAGES file like that you can cause issues for your user.

## Repository configuration

Inside your RELEASE file you will be able to configure your repository you must lay it out like this

```
Origin: Clarity
Label: Clarity
Suite: stable
Version: 1.0
Codename: ios
Architectures: iphoneos-arm
Components: main
Description: This is the default repository for Clarity Package Installer.
```

### Create a package

To create a package make a folder with the package name and then create a folder structure to where the package is installed like the lotus_icon_mask is set out.

```
Folder Structure: /System/Library/PrivateFrameworks/MobileIcons.frameworks
```
Once you have done that create a tar.gz file by editing packages.sh and adding your packages for instance

```
tar -zcvf PACAKGE_NAME.tar.gz PACKAGE_FOLDER_NAME
```

```
tar -zcvf lotus_icon_mask.tar.gz lotus_icon_mask
tar -zcvf custom_carrier.tar.gz custom_carrier
```

### Updating Repository

To Update your repository just run update.sh in the command line
