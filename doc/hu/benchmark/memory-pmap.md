# Memóriamérés

## Metodika

### Ideális

A leghasznosabb és legigazibb lenne ha valódi (virtuális) gépen adott RAM beállítással lefuttatnánk a forgatókönyvet (például egymás után adott weboldalak megnyitása), és addig csökkentenénk a RAM beállítást amíg el nem kezd használhatatlanságig swapelni. Ez lenne az adott program/forgatókönyv empirikus RAM igénye. Ez már a zram tömöríthetőséggel is számolna.
Közelítés

### Futtatás

Egy futó alkalmazás hatására az Xorg, a kernel és 1-2 egyéb rendszerfolyamat által foglalt memória mérete is jelentősen növekedhet, ezért reálisabb képet mutat ha a program futása közben mérhető, a teljes rendszer által lefoglalt memóriát (free: usage) levonjuk a kilépés után mérhető foglalásból

### Kézi pmap parancsok

```
for MODE in "r-x--" "r--[s-]-" "r[w-][x-]s-" "rw[x-]--"; do
 echo $MODE;
 pgrep -f "^/usr/lib/libreoffice/program/soffice.bin --impress " |
 xargs pmap -x |
 grep " $MODE " |
 tr -s " " |
 cut -d " " -f 3 |
 awk '{s+=$1}END{print s}';
done

pgrep -f "^/usr/lib/libreoffice/program/soffice.bin --impress " |
xargs pmap -x |
grep " r[w-][x-]-- " |
tr -s " " |
cut -d " " -f 4 |
awk '{s+=$1}END{print s}'
```

## Eredmények

## loimpress pmap

amd64, "^/usr/lib/libreoffice/program/soffice.bin --impress "

### Ubuntu 16.04

loimpress 5.1.6.2 megnyitás, üres dokumentum

* 122MB RSS, 79MB kód, 9MB adat, 5MB megosztott, 32MB írható, összesen 36MB privát dirty

Megnyitás, benne 4 egyszerű dia: szöveg, grafikon, táblázat, kép (TODO: igazi érettségi feladattal)

* 157MB RSS, 96MB kód, 11MB adat, 5MB megosztott, 48MB írható, összesen 53MB privát dirty

### Ubuntu 18.04

loimpress 6.0.7.3 megnyitás, üres dokumentum (sablon varázslóra cancelt nyomtam)

* RSS 162MB, 115MB kód, 12MB adat, 3MB osztott, 36MB írható, összesen 43MB privát dirty

Megnyitás, benne 4 egyszerű dia: szöveg, grafikon, táblázat, kép (TODO: igazi érettségi feladattal)

* RSS 184MB, 128MB kód, 14MB adat, 3MB osztott, 42MB írható, összesen 52MB privát dirty
* Ez egy lassabb gépen volt (1.5GHz Ivy Bridge + 2.5" 500GB HDD) és mégis szubjektíven hamar betöltött és nagyon kellemesen gyorsan reagált a kattintásokra.

## Firefox PeerTube, loImpress, free, df

amd64, 2GB RAM, `free` és `df` parancsok

### Ubuntu 20.04

* df / 5.8GB
* memory used 776236 kB: friss boot üresen
* memory used 1383184 kB: Firefox https://tube.grin.hu/ + LoImpress üres dokumentum
* memory used 864468 kB: üresen utána

### Kubuntu 20.04

* df / 6.5GB
* memory used 993204 kB: Firefox https://tube.grin.hu/ + LoImpress üres dokumentum
* memory used 559080 kB: üresen utána
* memory used 720064 kB: LoWriter
* memory used 1053520 kB: Firefox + LoWriter
* memory used 1075348 kB: Firefox + LoWriter + LoImpress

### Xubuntu 20.04

* df / 5.5GB
* memory used 1003452 kB: Firefox https://tube.grin.hu/ + LoImpress üres dokumentum
* memory used 490728 kB: üresen utána

### Lubuntu 20.04

* df / 4.8GB
* memory used 747136 kB: Firefox https://tube.grin.hu/ + LoImpress üres dokumentum
* memory used 370760 kB: üresen utána
