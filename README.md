# opkg-extras
The repository at hand takes up on the script presented in the name-giving [opkg_extras](https://openwrt.org/docs/guide-user/advanced/opkg_extras) article part of the OpenWRT documentation and frames it into an installable package.

## Status
Please note: The package has been subjected to non-exhaustive internal tests and is therefore not cleared for productive use.

## Manual Updates
```opkg install https://github.com/resmh/opkg-extras/releases/download/latest/opkg-extras.ipk```

## Automatic Updates
- Add releases to your ```/etc/opkg/customfeeds.conf```:

```src opkg_extras https://github.com/resmh/opkg-extras/releases/download/latest```

- Upload ```opkg_extras.signify.pub``` from this repository to a temporary location

```/tmp/opkg_extras.signify.pub```

- Associate key with opkg

```opkg-key add /tmp/opkg_extras.signify.pub```

- Delete temporary file, call ```opkg update``` and finally ```opkg install opkg-extras```
