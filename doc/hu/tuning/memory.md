# Memóriatakarékosság

## cgroups

* https://raymiiorg.github.io/articles/Limit_specific_process_memory_on_desktop_linux_with_cgroups.html

> Limit specific process memory on desktop linux with cgroups and earlyoom

## Reserved huge pages

Mérhetően javítja a nagy memória igényű tudományos alkalmazások futtatását.
Talán javíthatná a HDD swap viselkedést ha nagyobb, folytonos blokkokat írnánk ki a memóriából és nem random 4kB-ot. A (jelenleg elérhető) swap eszközök a page size-hoz vannak kötve.

* https://kerneltalks.com/services/what-is-huge-pages-in-linux/

Egyéni szoftvertámogatás szükséges:

* Qemu/KVM https://help.ubuntu.com/community/KVM%20-%20Using%20Hugepages
* Xen
* MySQL https://dev.mysql.com/doc/refman/5.7/en/large-page-support.html
* PostgreSQL
* Java
* memcached
* https://wiki.debian.org/Hugepages#Hugepage_enabled_applications

## Transparent huge pages

Hasonló előnyöket hordoz mint a hagyományos hugepages egy kevés futási idejű felár mellett.
Fegyelmezett használattal gyorsíthatjaja a tudományos alkalmazásokat is

* https://alexandrnikitin.github.io/blog/transparent-hugepages-measuring-the-performance-impact/

Bekapcsolás:

```
echo defer > /sys/kernel/mm/transparent_hugepage/defrag # HPC: always
echo always > /sys/kernel/mm/transparent_hugepage/enabled
echo always > /sys/kernel/mm/transparent_hugepage/shmem_enabled # HPC: force
sed -i "s/GRUBCMDLINE_LINUX_DEFAULT=\"/&transparent_hugepage=always /" /etc/default/grub
```
