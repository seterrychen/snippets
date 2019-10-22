## Install
```
pip install docopt
```


## Usage
### Basic usage
```
"""Naval Fate.

Usage:
  naval_fate.py ship new <name>...
  naval_fate.py ship <name> move <x> <y> [--speed=<kn>]
  naval_fate.py ship shoot <x> <y>
  naval_fate.py mine (set|remove) <x> <y> [--moored | --drifting]
  naval_fate.py (-h | --help)
  naval_fate.py --version

Options:
  -h --help     Show this screen.
  --version     Show version.
  --speed=<kn>  Speed in knots [default: 10].
  --moored      Moored (anchored) mine.
  --drifting    Drifting mine.

"""
from docopt import docopt


if __name__ == '__main__':
    args = docopt(__doc__, version='Naval Fate 2.0')
```

if input `ship Guardian move 10 50 --speed=20`, the args will be
```
{
  "--drifting": false, 
  "--help": false, 
  "--moored": false, 
  "--speed": "20", 
  "--version": false, 
  "<name>": [
    "Guardian"
  ], 
  "<x>": "10", 
  "<y>": "50", 
  "mine": false, 
  "move": true, 
  "new": false, 
  "remove": false, 
  "set": false, 
  "ship": true, 
  "shoot": false
}
```


## [online test tool](http://try.docopt.org/)
