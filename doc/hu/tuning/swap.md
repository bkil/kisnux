# Swap cseretár finomhangolás

## zram

* TODO: érdemes-e csökkenteni a block eszköz readaheadjét és egyéb tulajdonságát /sys/block/zram*/queue/*?
* https://www.kernel.org/doc/html/latest/admin-guide/blockdev/zram.html#writeback

### zram Ubuntu

```
apt install zram-config # ez reboot után mindent megcsinál
```

A hatékonyság növeléséért át lehet még szerkeszteni itt: /usr/bin/init-zram-swapping vagy lehet az /etc/rc.local-ba is tenni ilyesmit:

```
zramctl -f
echo 1 > /sys/block/zram0/reset
echo 2 > /sys/block/zram0/max_comp_streams # =1/CPU core
echo deflate > /sys/block/zram0/comp_algorithm # slower but much better
echo 2000000000 > /sys/block/zram0/disksize # in bytes
mkswap /dev/zram0
swapon --discard --priority=5 /dev/zram0 # discard might help reduce consumption when not used
```

### zram Fedora

```
dnf install zram
systemctl enable zram-swap.service
reboot
```

## zcache

hasonló a zramhoz csak még a page cache-et is tömöríti és tud swap háttértárral jól kooperálni

## zswap

ha jelentős méretű HDD swap is van, hatékonyabban működhet

https://en.wikipedia.org/wiki/Zswap

## Tömörített swap

(TODO: nem ismerek implementációt rá)

## GPU swap

Csak a vicc kedvéért, de tipikusan nem lesz GPU a gépben:
https://wiki.archlinux.org/index.php/Swap_on_video_RAM

## Egyebek

```
sysctl vm.swappiness=100
echo 32768 > /proc/sys/vm/admin_reserve_kbytes # TODO: fine tune
echo 500 > /proc/sys/vm/watermark_scale_factor
echo 2 > /proc/sys/vm/overcommit_memory # TODO
echo 200 > /proc/sys/vm/overcommit_ratio # TODO
echo 0 > /proc/sys/vm/page-cluster # HDD swapen ront, zram swapen használhat, TODO egyensúly, esetleg writeback backing device?
```
