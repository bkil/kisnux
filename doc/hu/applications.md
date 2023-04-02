# Felhasználói alkalmazások

## Bevezetés

* Legfontosabb alkalmazási kategóriák és esetlegesen pehelysúlyú alternatíváik.
* Nem célunk a világ összes szabad szoftverét és git tárolóját felsorolni.
  * Itt csak a mi szempontunkból érdekeseket vizsgáljuk: hogy a kicsi vagy a nagy gépen egyedül vagy 1-2 kisebb alkalmazás társaságában elfogadható teljesítménnyel használható-e
* Ideális volna a jelenleg karbantartott állapotúakra szorítkozni
  * Se nem elévült, se nem tervezés alatt álló
  * Használják elegen ahhoz, hogy ne csődöljön be a közeljövőben
  * Az átmenetileg elárvultakat bent hagyhatjuk külön jellel és időnként rá lehet nézni
* Ha találunk hozzá meglévő listát Wikipédián, lehetőleg az ott lévőre csak hivatkozzunk és ott bővítsük.

## Vizsgálandó

### Fájlkezelő

### Hálózati forgalom visszajelző

Mobilneten elhasznált és hátralévő adatátvitelt számoló, megjelenítő és figyelmeztető alkalmazás/widget

### Email kliens

* https://en.wikipedia.org/wiki/Balsa_(email_client)
* https://en.wikipedia.org/wiki/Claws_Mail
  * Elődje: https://en.wikipedia.org/wiki/Sylpheed
* https://en.wikipedia.org/wiki/GNOME_Evolution
* https://en.wikipedia.org/wiki/Geary_(e-mail_client)
* https://en.wikipedia.org/wiki/Mozilla_Thunderbird
  * Ennek talán része: https://en.wikipedia.org/wiki/SeaMonkey#Mail
* https://en.wikipedia.org/wiki/Kontact#E-Mail
* https://en.wikipedia.org/wiki/Mailpile
* https://en.wikipedia.org/wiki/Trojit%C3%A1
* Nem gyakran frissül https://en.wikipedia.org/wiki/GNUMail

### Hír aggregátor

RSS, Feed, Atom

* https://en.wikipedia.org/wiki/Liferea
* https://en.wikipedia.org/wiki/QuiteRSS
* Thunderbird
* https://en.wikipedia.org/wiki/GNOME_Evolution
* https://en.wikipedia.org/wiki/Claws_Mail
* https://en.wikipedia.org/wiki/Kontact#News_feed_aggregator Akregator
* https://addons.mozilla.org/firefox/collections/5975439/feed-readers/
* https://en.wikipedia.org/wiki/SeaMonkey
* terminálos, régi https://en.wikipedia.org/wiki/Canto_(news_aggregator)
* terminálos https://en.wikipedia.org/wiki/Gnus
* terminálos https://en.wikipedia.org/wiki/Newsbeuter
* https://en.wikipedia.org/wiki/Comparison_of_feed_aggregators

### Webalkalmazások kiváltására

Amennyiben egy általános böngészőnél takarékosabban is el lehet érni közismertebb weboldalakat, arra ne a böngészőt használjuk.

#### YouTube

Videó nézés bejelentkezés nélkül - nem hivatalos lejátszókkal

* https://github.com/omarroth/invidious 
  * van automatikusan átirányító böngésző kiegészítő (Privacy Redirect)
  * magyarítani szükséges
  * támogatja a "csak hangsáv" módot, sávszélességet és erőforrást spórolva (zene/előadás hallgatáshoz)
* QMplay
  * fapados beépített YouTube kliens
  * magyarítva van
  * támogatja a "csak hangsáv" módot
* https://freetubeapp.io/
* Inspiráció Raspberry Pi 4-ről (widget + localhost web server ami egy lokális lejátszóhoz pipe-ol)
  * https://www.linuxlinks.com/raspberry-pi-4-chronicling-desktop-experience-video-playback/

#### PeerTube

* QMplay2

#### TED.com

* QMplay2

#### Mastodon

* https://github.com/bleakgrey/tootle

### Böngésző

Szempontok:

* Használható legyen 1-ablakos böngészésre
* Elég legyen legfeljebb óránként bezárni
* Le kell benchmarkolni
  * Kompromisszumként elfogadható, hogy néhány közismertebb weboldalt a böngészőnél takarékosabb célalkalmazásban nyissanak meg a felhasználók

#### Blink alapú

* https://en.wikipedia.org/wiki/Chromium_(web_browser)
  - `apt install chromium-browser`
* https://en.wikipedia.org/wiki/Dooble
  - QtWebEngine
* https://en.wikipedia.org/wiki/Microsoft_Edge#New_Edge_(2019%E2%80%93present)
* KDE: https://en.wikipedia.org/wiki/Falkon
  - `apt install falkon`
* KDE: https://en.wikipedia.org/wiki/Konqueror
  - `apt install konqueror`
  - alapból Blink (QtWebEngine), de WebKit2 (QtWebKit) bővítmény is elérhető
  - https://github.com/KDE/kwebkitpart
* https://en.wikipedia.org/wiki/Otter_Browser
  - Blink (QtWebEngine) és WebKit (QtWebKit) választható
* https://en.wikipedia.org/wiki/Qutebrowser
  - Radikális, billentyűzetes az interfész
  - `apt install qutebrowser`
  - alapból Blink (QtWebEngine), de WebKit2 (libqt5webkit5) változat is elérhető: `qutebrowser-qtwebkit`
* https://en.wikipedia.org/wiki/SRWare_Iron

#### WebKit alapú

* https://en.wikipedia.org/wiki/GNOME_Web
  - `apt install epiphany-browser`
  - libwebkit2gtk
* https://en.wikipedia.org/wiki/Surf_(web_browser)
  - Kicsit szokatlan, billentyűzetes a vezérlése
  - `apt install surf`
  - libwebkit2gtk

#### KHTML alapú

* https://github.com/KDE/khtml
  - Ubuntu Focal és Debian Buster kiadásokig a Konqueror is ezt hasztálta

#### Gecko alapú

* https://en.wikipedia.org/wiki/Firefox
  - `apt install firefox`
* https://en.wikipedia.org/wiki/GNU_IceCat
* https://en.wikipedia.org/wiki/SeaMonkey
* https://en.wikipedia.org/wiki/Waterfox

#### Goanna

Régebbi Gecko forkja takarékossági és biztonsági megfontolásokból.

* https://en.wikipedia.org/wiki/Conkeror
  - Radikális, billentyűzetes az interfésze. Frissítendő Pale Moon-hoz.
* https://en.wikipedia.org/wiki/Pale_Moon_(web_browser)#Basilisk_browser
* https://en.wikipedia.org/wiki/Pale_Moon_(web_browser)

#### NetSurf

* https://en.wikipedia.org/wiki/NetSurf
  * Független, teljes értékű lehet, de egyes képességeinek a kompatibilitását ellenőriznünk kell
  * GTK és Linux Framebuffer támogatás
  * Bizonyos verziókban kísérleteztek SpiderMonkey bekötésével
  * Egyes változatokban takarékos JavaScript interpreter:
  * https://duktape.org/
  * https://kangax.github.io/compat-table/es6/

#### SerenityOS LibWeb

* https://en.wikipedia.org/wiki/SerenityOS
  * https://github.com/SerenityOS/serenity/tree/master/Userland/Applications/Browser
  * https://github.com/SerenityOS/serenity/tree/master/Userland/Libraries/LibWeb
* https://github.com/SerenityOS/serenity/tree/master/Ladybird
  * https://awesomekling.github.io/Ladybird-a-new-cross-platform-browser-project/

#### Kompromisszumos grafikus böngészők

* Dillo
  - már nem fejlesztik, és fejlesztendő a Javascript/CSS
* `links2 -g`
  - TODO Javascript/CSS bár egyes klónokban elkezdték régen és ebben is volt Netscape 1.1
* hv3: CSS (2008) és opcionális régebbi JavaScript (ES3, 2009) támogatással
  - https://packages.debian.org/bullseye/hv3
* https://github.com/CMB/edbrowse
  - szöveges, régen DukTape JavaScript, újabban QuickJS
  - `apt install edbrowse`
* https://github.com/alandipert/ncsa-mosaic
* TODO: Szerver oldali rendering
  * https://gitlab.com/bkil/freedom-fighters/-/blob/master/hu/server/optimizing-web-proxy.md#szabad-proxy-p%C3%A9ld%C3%A1k

#### Elévült böngészők

* https://github.com/ekapujiw2002/kweb
  - régen nincs frissítve
* https://en.wikipedia.org/wiki/Midori_(web_browser)
  - `apt install midori`

#### Weboldalak reprezentatívan

Bonyolultság szempontjából ezeket tekinthetjük etalonnak.
Ezen benchmarkolunk és optimalizálunk.
Nem számoljuk azokat amire célalkalmazás elérhető.
Főleg bekiabálás útján írtuk össze, szabad bővíteni.

* Bitchute
* (PeerTube)
* Mastodon
* Diaspora
* Friendica
* BBB
* Jitsi
* Moodle
* EtherPad
* EtherCalc
* Framadate
* GetTogether
* Mobilizon
* DuckDuckGo.com qwant.com mojeek.com
* Wikipedia.org
* Híroldalak: CNN.com bbc.co.uk ArsTechnica.com hvg.hu 444.hu g7.hu sg.hu SzabadEuropa.hu Telex.hu
* CryptPad
* NextCloud
  * fájltallózó
  * jegyzettömb https://apps.nextcloud.com/apps/notes

#### Weboldalak kíváncsiságból

* https://m.youtube.com/ Android user-agent beállítással
* Youtube nem multimédiás fióktevékenységek: bejelentkezés, dashboard, lájkolás, kommentálás, (videó feltöltés?)
* Facebook
* Twitter
* TED.com
* https://github.com/mozilla/gecko-dev/blob/f36437a53e3b5d16cfba7a177291f3c5ff5ddd24/testing/perfdocs/generated/raptor.rst
* https://github.com/mozilla/gecko-dev/blob/669bffcf00fc352e27b7cbc12e46f711f96c4cc5/testing/performance/sites.txt
* Luxus böngészendő oldalak az erősebb konfiguráción
  * rtlmost.hu
* NextCloud videólejátszó, videocset

#### Böngésző kiegészítők

Akár lehetne egy részét szerver oldali proxy-n is futtatni (vagy localhost) a böngésző helyett

Gyorsítás:

* uBlock Origin
* h264ify
* uMatrix
  - kellene egy központi alapértelmezett blokkoló lista, mert sok idő betanítani
* LocalCDN
* Privacy Badger
* Privacy Possum

Magánszféra:

* Privacy Pass
* Privacy Redirect
* HTTPS Everywhere
* ClearURLs

Ilyesmivel tudnánk kézzel készíteni a leggyakoribb weboldalak megjelenítéséhez egyszerűsítő szabályokat:

* Stylus
* ViolentMonkey

### Cset kliens

* ? Matrix
* ? XMPP

### VoIP + videó telefonálás

320x240 15 fps?

* ?LinPhone
* Matrix Nheko klienssel (még nem aktuális, idei GSOC-ra van kitűzve)

#### MJPEG

Az olcsó webkamerák is majdnem mindig tudják sok felbontásban a hardveres MJPEG tömörítést (a drágábbak h264-et is) - esetleg erre valami kliens támogatás?
A DCT ábrázolás miatt lehet minimális számítással és egy kis tömörítési arány veszteséggel felezni, esetleg negyedelni a felbontást (nyolcadolás már tömörítetlen), valahol láttam ilyen toolt még régen ami JPEG-aware módon transzformált fájlokat.

`v4l2-ctl --list-formats-ext -d /dev/video0`

* Régi Acer netbook: 160x120 .. 1280x720 16/30fps
* Dell laptop: 960x540 .. 1280x720 15/30fps
* Két különböző, régi, 1000Ft-os webkamera: 160x120 .. 640x480

```
mplayer -dumpfile x.mjpeg -dumpvideo -fps 15 -tv device=/dev/video0:driver=v4l2:outfmt=mjpg:width=960:height=540:fps=15 tv:// # bár az fps állítás ezen nem mindig működik csak lejátszáskor
ffmpeg -f v4l2 -video_size 160x120 -framerate 15 -input_format mjpeg -i /dev/video0 -vcodec copy -t 10 -an -r 15 -y x.avi # 400 kb/s
ffmpeg -f v4l2 -video_size 320x240 -framerate 15 -input_format mjpeg -i /dev/video0 -vcodec copy -t 10 -an -r 15 -y x.avi # 1.4Mb/s
ffmpeg -f v4l2 -video_size 960x540 -framerate 15 -input_format mjpeg -i /dev/video0 -vcodec copy -t 10 -an -r 15 -y x.avi  # 12Mb/s
```

### Webrádió/online streaming

* VLC

### Lokális zenehallgatás

ogg, mp3, aac, trackelt module-ok, akár földfelszíni vagy műholdas sugárzásról

* VLC
* XMMS2
* Deadbeef https://github.com/DeaDBeeF-Player/deadbeef
* Timidity: midi
* XMP: mod/s3m
* (? QMMP, MilkyTracker, modplug-tools.)

### Jegyzettömb

* https://joplinapp.org/
* https://turtlapp.com/
* https://en.wikipedia.org/wiki/Zim_(software)
* https://github.com/giuspen/cherrytree
* https://github.com/FoxUSA/OpenNote
* https://github.com/zadam/trilium
* https://github.com/BijoySingh/Scarlet-Notes Android

### Szövegszerkesztő

Akár saját célra.

* Abiword (TODO: teszt)
* LibreOffice Writer: hatalmas, érettségi
  * https://em.wikipedia.org/wiki/Apache_OpenOffice
* https://en.wikipedia.org/wiki/Calligra_Words
* https://en.wikipedia.org/wiki/GNU_TeXmacs
* https://en.wikipedia.org/wiki/LyX

### Táblázatkezelő

érettségi vagy saját célra

* Gnumeric (TODO: teszt)
* LibreOffice Calc: hatalmas, érettségi
* https://en.wikipedia.org/wiki/Calligra_Sheets
* https://en.wikipedia.org/wiki/Pyspread

### Fapados rajzolóprogram

* mtpaint

### Gazdag vizualizációs önkifejezés

Akár hobbi vagy továbbképzési célra.

* Inkscape: hatalmas, érettségi
* LibreOffice Draw: hatalmas, érettségi
* Gimp: hatalmas, érettségi
* https://en.wikipedia.org/wiki/Calligra_Flow
* https://en.wikipedia.org/wiki/Vym_(software) (mindmap)
* https://en.wikipedia.org/wiki/Karbon_(software)
* https://en.wikipedia.org/wiki/Krita
* https://en.wikipedia.org/wiki/Scribus

### Adatbázis

* MySQL
* PostgreSQL: érettségi

Adatbázis GUI:

* sqlitebrowser
* LibreOffice Base: hatalmas, érettségi
* https://en.wikipedia.org/wiki/Kexi

### Honlapkészítés

Érettségire:

* Bluefish
* BlueGriffon
* Mozilla Compozer
* KompoZer
* TODO: kellene valami forrásszintű HTML/CSS szerkesztő és/vagy oktatóprogram

### Prezentáció készítés

* LibreOffice Impress: érettségi
* https://en.wikipedia.org/wiki/Calligra_Stage

### Programozás IDE érettségire

* IDLE
* Code::Blocks (+ wxSmith)
* Eclipse: hatalmas
* NetBeans: hatalmas
* Free Pascal
* Lazarus: hatalmas?
* Geany
* QtCreator

### Programozási fejlesztőeszközök

Bonyolultabb, de várhatóan reálisan futtatható intelligens fejlesztőeszközök hobbira vagy felkészülés a munkára.

* https://en.wikipedia.org/wiki/FLUID
* https://en.wikipedia.org/wiki/GNOME_Builder#Features
* https://en.wikipedia.org/wiki/Glade_Interface_Designer#Code_sketching
* https://en.wikipedia.org/wiki/Anjuta#Features
* https://en.wikipedia.org/wiki/CodeLite
* https://wiki.codelite.org/pmwiki.php/Main/WxCrafter
* https://en.wikipedia.org/wiki/WxFormBuilder
* https://en.wikipedia.org/wiki/Gambas
* https://en.wikipedia.org/wiki/Nemiver
* https://github.com/alejandroautalan/pygubu (Python tkinter RAD)
* https://en.wikipedia.org/wiki/Data_Display_Debugger
* https://en.wikipedia.org/wiki/Scratch_(programming_language)
* https://en.wikipedia.org/wiki/Comparison_of_integrated_development_environments
* https://en.wikipedia.org/wiki/Graphical_user_interface_builder
* TODO: kéne valami JavaScript szerkesztésre is honlapszerkesztéshez

### Videóvágás

A nagyobbik gépre**.

#### Cross platform videóvágás

* https://en.wikipedia.org/wiki/Avidemux
* https://en.wikipedia.org/wiki/Blender_(software)
* https://en.wikipedia.org/wiki/Cinelerra
* https://en.wikipedia.org/wiki/Kdenlive
* https://en.wikipedia.org/wiki/Natron_(software)
* https://en.wikipedia.org/wiki/Shotcut
* https://en.wikipedia.org/wiki/OpenShot_Video_Editor

#### Linux videóvágás

* https://en.wikipedia.org/wiki/Flowblade
* https://en.wikipedia.org/wiki/LiVES
* https://en.wikipedia.org/wiki/PiTiVi

### Távsegítséghez asztalmegosztás

* VNC
* rdesktop

### Szórakozás

#### Oktatójátékok kicsiknek

Lehetne ebben külön rész az oktató célú játékokról, azon belül akár kifejezetten a digitális írástudást segítőkről, pl. egérhasználat, vadászat 1-1 betűre a fránya klaviatúrán, stb.

* http://www.doudoulinux.org/web/english/documentation-7/applications-13/article/educational-games.html
* Gamine
* Pysycache
* Tux Paint
* Childsplay
* Gcompris
* Tictactoe-ng
* Raincat
* Klettres
* Ktuberling
* Khangman
* Kanagram
* Tanglet
* Marble
* Kgeography

#### Játékok

Egy központi játékválogatást is karban lehetne tartani mert számtalan akad, de ez egy külön dokumentum lesz szerintem

* http://www.doudoulinux.org/web/english/documentation-7/applications-13/article/fun-games.html
* https://en.wikipedia.org/wiki/List_of_open-source_video_games
* https://en.wikipedia.org/wiki/List_of_commercial_video_games_with_available_source_code
* https://en.wikipedia.org/wiki/List_of_commercial_video_games_with_later_released_source_code
* https://en.wikipedia.org/wiki/List_of_commercial_video_games_released_as_freeware
* https://libregamewiki.org/
* https://freegamer.blogspot.com/
* https://osgameclones.com/
* https://trilarion.github.io/opensourcegames/
* https://github.com/leereilly/games/blob/master/README.md
* https://curlie.org/Computers/Open_Source/Software/Games
* https://directory.fsf.org/wiki/Category/Game
