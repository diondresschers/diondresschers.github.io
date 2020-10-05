
# bash - notdefault

## bash - xclip

You can put data in the clipboard which you can later paste in bash with <MOUSE-MIDDLE-CLICK>


```bash
uptime | xclip
xclip -o # outputs the data from clipboard
```

You can also higlight data in bash and then paste again with <MOUSE-MIDDLE-CLICK> or with `xclip -o`.

You can sent the copied data to the OS clipboard with, so you can use this data in any other GUI application:

```bash
xclip -selection clipboard
```

So:

```bash
uptime | xclip -slection clipboard
uptime | xlc
alias | grep xclip
alias xcl='xclip -selection clipboard'
```


# emulation

## emulation - qemu

* [Emulate Raspberry Pi with QEMU | Azeria Labs](https://azeria-labs.com/emulate-raspberry-pi-with-qemu/)

Get an [ARM Raspberry Pi version](http://downloads.raspberrypi.org/raspbian/images/raspbian-2017-04-10/)

Get the latest [QEMU emulation](https://github.com/dhruvvyas90/qemu-rpi-kernel)

```bash
mkdir ~/qemu_vms/
# put the Raspeberry Pi *.img file in this folder
sudo apt-get install qemu-system -y
fdisk -l 2019-07-10-raspbian-buster-full.img

```

## retropie

* [How to install RetroPie on Ubuntu | Tutorial | MARKO NTECH](https://markontech.com/linux/how-to-install-retropie-on-ubuntu-tutorial/)

```
sudo apt-get install -y git dialog unzip xmlstarlet
git clone --depth=1 https://github.com/RetroPie/RetroPie-Setup.git
cd RetroPie-Setup
sudo ./retropie_setup.sh
```

To run retropie:

```
emulationstation
```

To add roms:
```:q
dion@desktop:~/RetroPie$ tree
.:q!
├── BIOS
├── retropiemenu
│   ├── bluetooth.rp
│   ├── configedit.rp
│   ├── esthemes.rp
│   ├── filemanager.rp
│   ├── icons
│   │   ├── audiosettings.png
│   │   ├── bluetooth.png
│   │   ├── configedit.png
│   │   ├── esthemes.png
│   │   ├── filemanager.png
│   │   ├── raspiconfig.png
│   │   ├── retroarch.png
│   │   ├── retronetplay.png
│   │   ├── rpsetup.png
│   │   ├── runcommand.png
│   │   ├── showip.png
│   │   ├── splashscreen.png
│   │   └── wifi.png
│   ├── retroarch.rp
│   ├── retronetplay.rp
│   ├── rpsetup.rp
│   ├── runcommand.rp
│   └── showip.rp
└── roms
    ├── amstradcpc
    ├── atari5200
    ├── atari800
    ├── n64
    ├── ngp
    ├── ngpc
    └── pcengine

11 directories, 22 files

```

