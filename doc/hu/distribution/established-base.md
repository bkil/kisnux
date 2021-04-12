# Linux disztribúció amire alapozhatunk

* Kérem jelölje magát aki tapasztalattal vagy affinitással rendelkezik az adott kérdésben

## Előnyös

### Debian

* +kísérleti támogatás X32-re (64-bites operandusok, 32-bites címtér, kevesebb RAM fogyasztás):
  * https://wiki.debian.org/X32Port
* https://wiki.debian.org/AutomatedInstallation
* Talán nem a legnagyobb magyar közösség
  * https://hup.hu/Debian
  * https://hup.hu/forum/135
  * https://prohardver.hu/tema/debian_gnu_linux/friss.html
* @bkil, @crafterix (+a legtöbbünk)

### Lubuntu/Xubuntu/Ubuntu

* +Magyar közösség
  * http://ubuntu.hu/forum
  * https://hup.hu/Ubuntu
  * https://www.facebook.com/ubuntuhu/ (12K követőnk van)
  * https://help.ubuntu.com/stable/ubuntu-help/index.html.hu
* @bkil (+a legtöbbünk)
* @meskobalazs: ezen belül csak a Xubuntu

### Linux Mint + Cinnamon

* +Magyar közösség
  * https://linuxmint.hu/
* @urbalazs?

## Kérdéses

### Void Linux (runit, musl)

* @notramo

### Alpine Linux (busybox, musl)

* @notramo

### Trisquel

* Ubuntu amiből kivették a zárt drivereket és blobokat
  * https://gitlab.trisquel.org/trisquel/ubuntu-purge/-/blob/master/purge-focal
* változatai:
  * Trisquel MATE: asztali környezet
  * Triskel: KDE
  * Trisquel mini: LXDE
* Abrowser: Firefox zárt kiegészítők nélkül
* hátrányai
  * nincs magyar közössége
  * a hiányzó codecek miatt az eleve szűkös magyar oktatóanyag készletnek és weboldalaknak csak egy részét tudnák használni
  * néhány hardverhez hiányzik vagy nem teljes funkcionalitású a FOSS (vagy blobmentes) meghajtó:
    * itt nem mi választjuk meg a hardvert (hálózat, kamera, hangkártya, nyomtató, szkenner, TV tuner, GPU, ...) - bár néha megoldható a csere, valakinek ki kell fizetnie az új perifériát
    * gyorsítás nélkül az eleve lassú gép használhatatlanná válhat sok feladatra
    * energiagazdálkodás nélkül hangosabb lehet a gép és többet fogyaszt, kevesebb ideig bírja az akku
    * altatási hiányosságok esetén vagy egyáltalán nem lehet altatni a gépet vagy néha lefagyhat ébredés után
* @matam
