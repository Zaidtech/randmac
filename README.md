randmac.py
==========

a utility that generates 12-digit mac addresses; either the NIC portion or full 12-digit MAC. 

the optional `-f` argument will return a random 12-digit MAC address that can be identified by the locally administrated address (LAA) format. This means you will always see `x2`, `x6`, `xA`, or `xE` at the beginning of a MAC address generated by randmac.

# installation

to install with pip:

`pip install randmac`

# requirements

Python >3.2 required.

# mac address formats

Supported MAC address formats:
 - MM:MM:MM:SS:SS:SS
 - MM-MM-MM-SS-SS-SS
 - MM.MM.MM.SS.SS.SS
 - MMMM.MMSS.SSSS
 - MMMMMMSSSSSS

where `M` stands for the manufacturer or vendor, and `S` stands for the NIC specific portion. 

# usage

requires a mac address as input. it is used to determine what the output format should be.

you can `from randmac import RandMac` and use it like `RandMac("00:00:00:00:00:00")`.

from a terminal (if the randmac.py is in your path and executable) you can use `$ python3 randmac.py 00:00:00:00:00:00` to get a generate a new NIC portion, or `$ python3 randmac.py 00:00:00:00:00:00 -f` to generate a new 12-digit LAA MAC.

# example usage

```
>>> from randmac import RandMac
>>> RandMac("00:00:00:00:00:00")
'00:00:00:00:fd:9e'
>>> RandMac("00:00:00:00:00:00", True)
'ba:ac:5f:09:fc:bb'
>>> RandMac("0000.0000.0000", True)
'fe84.857f.900f'
```

or

```
$ python3 randmac.py 00:00:00:00:00:00
00:00:00:fc:e1:5b
$ python3 randmac.py 00:00:00:00:00:00 -f
2a:81:b0:e7:1d:08
``` 

# license

license can be found [here](https://github.com/joshschmelzle/randmac/blob/master/LICENSE).
