# dlnap
Enjoy your favorite music on your favorite sound system over your local network.  
Simple network player for DLNA/UPnP devices allows you discover devices and playback your favorite media on them.

## Requires
 * Nothing but python (whatever you like: python 2.7+ or python3)
 
## TODO
- [ ] Stop/Pause playback
- [ ] Set next media
- [ ] Integrate local http server to allow playback local files
- [ ] Investigate if it possible to play images/video's on DLNA/UPnP powered TV
 
## Supported devices
 * Yamaha RX577
 * _please email me if it works or doesn't work with your device_
 
## Usage
### Overview
```
dlnap.py [--list] [--ip <device ip>] [-d[evice] <name>] [-t[imeout] <seconds>] [--play <url>] [--all]
```
### Discover UPnP devices
**List compatible devices**
```
> dlnap.py --list
Discovered devices:
 [a] Receiver rx577 @ 192.168.1.40
```

**List all UPnP devices**
```
> dlnap.py --list --all
Discovered devices:
 [x] ZyXEL Keenetic Giga @ 192.168.1.1
 [x] Data @ 192.168.1.50
 [a] Receiver rx577 @ 192.168.1.40
```  
where  
**[a]** means that devices allows media playback  
**[x]** means that device doesn't allow media playback  


### Playback media
**By ip address**
```
dlnap.py --ip 192.168.1.40 'http://somewhere.com/my_favorite_music.mp3'
Receiver rx577 @ 192.168.1.40
```

**By device name**
```
dlnap.py --device rx577 --play 'http://somewhere.com/my_favorite_music.mp3'
Receiver rx577 @ 192.168.1.40
```
Note: a part of the device name is quite enough: *rx577* instead of *Receiver rx577*

**Any compatible device**
```
dlnap.py --play 'http://somewhere.com/my_favorite_music.mp3'
Receiver rx577 @ 192.168.1.40
```
