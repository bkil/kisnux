# Háttértár optimalizás

## hdparm

* Régi gépeken érdemes alaposan átolvasni a man-t és bekapcsolni/felemelni amit csak lehet mert többszörös sebességet tud hozni és csökkentheti a CPU használatot
  * Benchmark: `hdparm -t /dev/sda` vagy dd `if=/dev/sda bs=42M count=2 skip=42 iflag=direct of=/dev/null`
  * iozone -e -I -a -s 256M -r 4k -i 0 -i 2

## HDD particionálása

* Ellenőrizzük az adatlapban a szektor méretet és legalább ekkora alignment legyen minden partíció kezdetén (1MB biztos elég)
* A partíciók méretét minimalizálni kell, és biztosítani, hogy egymáshoz minél közelebb kerüljenek a seek műveletek.
* A fragmentáció ellen tűzzel-vassal kell védekezni, amihez nagy segítség ha minél gyakrabban használnánk egy partíciót, annál több helyet hagyunk rajta (pl. >20%).
* Mérhetően a HDD eleje a leggyorsabb mind lineáris átvitel, mind bájtban mért seek-távolságban szempontjából.
* Teljesítmény okokból javasolt titkosítást csak a felhasználfó adatpartíciójára vagy adatfájljaira rakni, esetleg a /etc/ vagy /var/-ban hogyha van valami személyes.

### Példa partícionálás

80GB HDD-re:

* 8GB / (vagy amennyi kell az alap programoknak és frissítéseknek),
* 2GB swap (0.5GB felett sokat lassul, csak vészhelyzetre)
* ha sok appot rakunk fel, esetleg az /usr-nek külön,
* 5GB /home és /tmp (vagy gyakran változó scratchpad, amennyi kell)
* ~60GB a maradék egyben hosszú távú, ritkán változó, nagy fájloknak
* 0.5GB boot (ha sok OS van 1GB)

## Flash/SSD partícionálás

* Ellenőrizzük az adatlapban az erase/write block méretet és legalább ekkora alignment legyen minden partíció kezdetén (pár megabájt szokott lenni)
* Nagyon olcsó flash hardvereken mint az SD kártyák, pendrive-ok és régi SSD-k korlátozott a nyitva tartható erase blokkok száma és az algoritmus sem túl hatékony. Ezért bonyolultabb fájlrendszerek egyre rosszabbul teljesítenek rajta (FAT -> ext2 -> ext3 ...), illetve minél több írható fájlrendszer van az eszközön, annál rosszabb a helyzet.
* A btrfs és más log structured fájlrendszer elvileg barátságosnak számít ilyen szempontból. De mégis hatékonyabb írható root, home és swap helyett ha csak a var és swap írható, a root pedig readonly + tmpfs overlay.

## Fájlrendszerek

* advanced: read-only squashfs root (zstd`**`, lz4++, xz, gzip, lzo) + ext4 vagy btrfs overlay (lzo++, zstd`**`, zlib) frissítéseknek (lásd: Puppy Linux), sokat gyorsíthat
  * https://forums.gentoo.org/viewtopic-t-646289-highlight-aufs+squashfs.html
  * https://elinux.org/Squash_Fs_Comparisons
  * https://quixdb.github.io/squash-benchmark/unstable/
  * https://en.wikipedia.org/wiki/Zopfli Ha elbírja a gép a gzip kitömörítést, ezzel lehetne további root helyet megtakarítani
* Ha ezt be lehetne küldeni a kernelbe, +10% gzip sebességet nyernénk:
  * https://github.com/emmanuel-marty/em_inflate
  * https://tech.marksblogg.com/faster-zip-decompression-unzip-deflate-zlib-crc32-adler32-7zip-archiver.html
  * https://github.com/ebiggers/libdeflate
  * https://github.com/zlib-ng/zlib-ng
* mksquashfs sort opcióval lehet sorba rakni a fájlokat használat szerint
  * Kapcsolódó https://github.com/AppImage/AppImageKit
* btrfs
  * block méretet érdemes kicsit megnövelni az alap 4kB-ról, hogy kevesebb CPU-t és I/O sávot vegyen el a feldolgozás és egy picit csökkentse a fragmentáció lehetőségét (nagyon megnövelve a sok üres hely okozta hatékonyság csökkenés miatt romlik a sáv kihasználása)

## Preload

* `apt install preload`
* Előre RAM-ba tölti a gyakran használt alkalmazásokat
* https://askubuntu.com/questions/110335/drawbacks-of-using-preload-why-isnt-it-included-by-default
* Kicsit pazarló nálunk, de ez alapján talán ki tudnánk alakítani a fájlok sorrendjét

## mount opciók

Hatásuk általában csak új írásokra vonatkozik, így érdemes még telepítés előtt beállítani

* általános
  * noatime,
  * lazytime
* btrfs-specifikus
  * compress=lzo (gyorsabb gépen compress=zlib) https://btrfs.wiki.kernel.org/index.php/Compression
  * autodefrag,
  * ssd_spread,
  * discard (vagy cron.daily fstrim, mert régi SSD-ken ronthatja a hatékonyságot a menet közbeni trimmelés)
  * inode_cache: azt írják bugos, de jó lenne
  * max_inline: nem tudom mennyi a default
  * nobarrier: nem jó ötlet de kíváncsi volnék az impactra, azt írják 3% körüli,
  * thread_pool=<magok száma>: a default magok száma+2, de HT-s Atom procin ez lehet, hogy sok
* ext4-specifikus
  * commit=20
  * max_batch_time=50000

## TODO

* blockdev --setfra ... --setra ...
* sysfs
* procfs
* sysctl
  * https://unix.stackexchange.com/questions/30286/can-i-configure-my-linux-system-for-more-aggressive-file-system-caching
  * https://cromwell-intl.com/open-source/performance-tuning/disks.html
  * https://wiki.archlinux.org/index.php/Improving_performance#Tuning_I/O_scheduler
