## Usage
### Install Backport packages
```
$ echo "deb http://archive.ubuntu.com/ubuntu codename-backports main restricted universe multiverse" | sudo tee -a /etc/apt/sources.list
$ sudo apt update
$ sudo apt install -t codename-backports package_name
```

### Just security updates
```
$ # to dump security list
$ sudo sh -c 'grep ^deb /etc/apt/sources.list | grep security > /etc/apt/sources.security.only.list'
$ # to list packages which need to upgrade on stdout
$ apt-get -s dist-upgrade -o Dir::Etc::SourceList=/etc/apt/sources.security.only.list -o Dir::Etc::SourceParts=/dev/null | grep "^Inst" | awk -F " " {'print $2'}
$ # to install packages which has security patch
$ apt-get -s dist-upgrade -o Dir::Etc::SourceList=/etc/apt/sources.security.only.list -o Dir::Etc::SourceParts=/dev/null | grep "^Inst" | awk -F " " {'print $2'} | xargs apt-get install
```
