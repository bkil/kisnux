# Ötlet merítésnek régi gépeket támogató aktuális disztribúciók

## Puppy Linux

* +Tesztelik 512MB és ennél is kisebb gépeken alap dolgokra
* +Tömörített fájlrendszer miatt gyorsan indulnak a dolgok, RAM-ba is elfér akár az egész
* +Pale Moon böngészőt választották alapértelmezettnek
* -Magyarítandók a saját menedzsment eszközei
* -UX szempontból sem egységesen kialakítottak a saját alkalmazásai
* -Sok alkalmazása nagyon kompromisszumos funkcionalitásban
* -Nem generálnak automatikusan frissítést pedig nem volna lehetetlen - Ubuntu Bionic repóból is tud építkezni

## mxlinux

* https://mxlinux.org/
* XFCE, KDE, Fluxbox

## Linux Lite

* Xfce + kezdőknek szóló GUI-k
* ?magyarítás
* https://en.wikipedia.org/wiki/Linux_Lite

## Android

* vagy akár Android X86?
* -Nem adnak ki hozzá frissítést (vagy max. 1 évig, utána kuka)
* -Sok produktivitáshoz köthető alkalmazás hiányzik
  * Továbbképzésekhez vagy munkához (pl. grafika, plakát terv, web design, webfejlesztés, programozás, újság tördelés, újságírás/bloggolás, irodai munka, zene szerkesztés`**`, videó vágás`**`/szerkesztés`**`), fordítás
  * Iskolához
  * Hardverismeretekhez szerelési gyakorlatokhoz
* -Natív Androidos eszközök drágábbak mint egy régi PC
* +Kevesebbet fogyaszt
  * Viszont mivel naponta csak keveset jár, a megtakarítás elhanyagolható

## Kutatás

* Extrémumként X11 nélkül is futhatnak egyes GUI alkalmazások:
  * DirectFB + GTK (az újabb GTK-ból azóta kivették) https://blog.nanl.de/2009/10/gtk2-running-on-top-of-directfb-on-openwrt/
  * DirectFB + FLTK (azt hiszem kísérleti) https://www.mail-archive.com/fltk-dev@easysw.com/msg00762.html
* Írhatunk vagy portolhatunk egyszerű célalkalmazásokat takarékos megoldásokkal (pl. FLTK, FOX, TK cross platform toolkit valamelyikével)
* Nano-X + FLTK https://en.wikipedia.org/wiki/Nano-X https://github.com/ghaerr/microwindows/
* Fejlesztőknek érdekes: teljesen új koncepció immediate mode rendering alapokon https://github.com/rxi/microui https://floooh.github.io/sokol-html5/sgl-microui-sapp.html

## Egyebek

* https://en.wikipedia.org/wiki/AntiX
  * Terjesztést akadályozó kitételt tartalmaz a licence!
  * https://en.wikipedia.org/wiki/ALT_Linux (rpm)

## Elemzésre vár

* https://q4os.org/ (Debian)
* https://en.wikipedia.org/wiki/Tiny_Core_Linux
* https://en.wikipedia.org/wiki/SliTaz
* https://en.wikipedia.org/wiki/Light-weight_Linux_distribution
* https://en.wikipedia.org/wiki/Alpine_Linux
* https://getalt.org/en/starterkits/
* TODO https://www.techradar.com/news/best-lightweight-linux-distro
* TODO http://www.linuxandubuntu.com/home/5-lightweight-linux-for-old-computers
