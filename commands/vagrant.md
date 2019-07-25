## Usage
### [Resize disk](https://gist.github.com/christopher-hopper/9755310)

### [How to set up a self-hosted "vagrant cloud" with versioned, self-packaged vagrant boxes](https://github.com/hollodotme/Helpers/blob/master/Tutorials/vagrant/self-hosted-vagrant-boxes-with-versioning.md)

### vagrant ssh to other user

Note: need to copy authorized_keys under `/home/vagrant/.ssh/` to specific user

```
  VAGRANT_COMMAND = ARGV[0]
  if VAGRANT_COMMAND == "ssh"
    config.ssh.username = 'ubuntu'
    config.ssh.private_key_path = '.vagrant/machines/default/virtualbox/private_key'
  end
```

