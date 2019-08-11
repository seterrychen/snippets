## Usage
### inspect disk image
```
fdisk -l disk.img

Disk /home/yjwong/disk.img: 250.1 GB, 250058268160 bytes
255 heads, 63 sectors/track, 30401 cylinders, total 488395055 sectors
Units = sectors of 1 * 512 = 512 bytes

   Device              Boot      Start         End      Blocks   Id  System
/home/yjwong/disk.img1            2048     3905535     1951744   82  Linux swap / Solaris
/home/yjwong/disk.img2   *     3905536   488394751   242244608   83  Linux
```
