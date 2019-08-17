## usage
### To test disk performance
```
$ dd if=/dev/zero of=out.file bs=512K count=2048 conv=fdatasync
```
```
options:
oflag=FLAGS    write as per the comma separated symbol list

  direct       use direct I/O for data
  dsync        use synchronized I/O for data
  sync         likewise, but also for metadata

conv=CONVS     convert the file as per the comma separated symbol list

  fdatasync    physically write output file data before finishing
  fsync        likewise, but also write metadata
```
