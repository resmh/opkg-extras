# opkg-extras
The repository at hand takes up on the script presented in the name-giving [opkg_extras](https://openwrt.org/docs/guide-user/advanced/opkg_extras) article part of the OpenWRT documentation and frames it into an installable package.

## Added Commands
opkg init|uci|import|save|restore|rollback|upgr|export|newconf|proc|reinstall

## Automatically Extend Root Partition and Restore Packages
Following the article, packages can be automatically restored upon first post-upgrade internet access. To enable this feature, touch /etc/opkg-restore. Based upon this, an experimental script to extend root partitions of sdX or mmcblkXpY type prior to package restoration has been added. To enable it, touch /etc/extendroot.

## Status
Please note: The package has been subjected to non-exhaustive internal tests and is therefore not cleared for productive use. This goes particularly for the extendroot script - do not use it without proper backups.

## Manual Updates
```opkg install https://github.com/resmh/opkg-extras/releases/download/latest/opkg-extras.ipk```

## Automatic Updates
Add repository, add repository key, update package lists and install:

```
echo 'src opkg_extras https://github.com/resmh/opkg-extras/releases/download/latest' >> /etc/opkg/customfeeds.conf; \
wget -O /tmp/opkg_extras https://github.com/resmh/opkg-extras/releases/download/latest/opkg_extras.signify.pub; \
opkg-key add /tmp/opkg_extras; \
rm /tmp/opkg_extras; \
opkg update; \
opkg install opkg-extras
```
