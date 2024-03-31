# Debugging Brother DS-740D on Ubuntu 23.10

Got the Sane Drivers from Brother website [^1].

Installed it with

```bash
dpkg -i --force-all brscan5-1.3.1-0.amd64.deb
```

And I see it installed with

```bash
dpkg -l | grep Brother
```

The kernel recognized it when connected to USB, but it is not attached
to /dev/

*output from dmesg*

```bash
[ 4659.303402] xhci_hcd 0000:00:14.0: Timeout while waiting for setup device command
[ 4659.543554] usb 4-1: new SuperSpeed USB device number 7 using xhci_hcd
[ 4659.567936] usb 4-1: New USB device found, idVendor=04f9, idProduct=0469, bcdDevice= 4.06
[ 4659.567946] usb 4-1: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[ 4659.567951] usb 4-1: Product: DS-740D
[ 4659.567954] usb 4-1: Manufacturer: Brother
[ 4659.567957] usb 4-1: SerialNumber: E80059E3X117246
```
When I run `lsusb` I see it here

```bash
Bus 004 Device 007: ID 04f9:0469 Brother Industries, Ltd DS-740D
```

But I still have no dev path.

**Fix**

Pluged it on another USB3 port on the back of my PC and now it work.
So the front USB was able to *read* the device, but did not loaded it on
`/dev/`

[^1]: <https://www.brother.co.uk/support/ds-740d/downloads>
