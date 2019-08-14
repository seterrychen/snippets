## Install
Alpine: `findutils`

## Usage

### find specific type and execute command
```
find . -name ".svn" -type d -exec rm -r "{}" \;
```

### find and filter by time
```
find . -newermt "2013-01-01 00:00:00"`

-newerXY reference
          Compares the timestamp of the current file with reference.   The
          reference  argument  is  normally the name of a file (and one of
          its timestamps is used for the comparison) but it may also be  a
          string  describing  an  absolute time.  X and Y are placeholders
          for other letters, and these letters select which time belonging
          to how reference is used for the comparison.

          a   The access time of the file reference
          B   The birth time of the file reference
          c   The inode status change time of reference
          m   The modification time of the file reference
          t   reference is interpreted directly as a time
```
