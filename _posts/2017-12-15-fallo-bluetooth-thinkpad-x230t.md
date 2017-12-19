---
layout: post
title: Error en el controlador de Bletooth en GNU/Debian Thinkpad X230T
---

Después de instalar GNU/Debian 9 en un Thinkpad X230 Tablet , casi todo funciona a la primera, sin embargo el Bluetooth da algunos problemas debido a que no carga correctamente el driver.

```

sudo dmesg | grep -i blue

bluetooth hci0: failed to load brcm/BCM20702A1-0a5c-21e6.hcd (-2)

```

Tenemos que descargar el driver correcto y guardarlo en la carpeta [/lib/firmware/brcm]:

```

~$ cd /lib/firmware/brcm
~$ sudo wget https://github.com/winterheart/broadcom-bt-firmware/raw/master/brcm/BCM20702A1-0a5c-21e6.hcd

```

Finalmente quitamos y volvemos a cargar el módulo del kernel o simplemente reiniciamos el ordenador:

```

~$ sudo modprobe -r btusb
~$ sudo modprobe btusb

```

Podemos comprobar nuevamente que el driver funciona:

```

~$ sudo dmesg | grep -i blue

[    3.230068] thinkpad_acpi: rfkill switch tpacpi_bluetooth_sw: radio is unblocked
[    4.741116] Bluetooth: Core ver 2.22
[    4.741135] Bluetooth: HCI device and connection manager initialized
[    4.741139] Bluetooth: HCI socket layer initialized
[    4.741143] Bluetooth: L2CAP socket layer initialized
[    4.741151] Bluetooth: SCO socket layer initialized
[    4.754080] Bluetooth: hci0: BCM: chip id 63
[    4.770145] Bluetooth: hci0: Broadcom Bluetooth Device
[    4.771042] Bluetooth: hci0: BCM20702A1 (001.002.014) build 1757
[    4.773877] bluetooth hci0: firmware: direct-loading firmware brcm/BCM20702A1-0a5c-21e6.hcd
[    4.844851] Bluetooth: BNEP (Ethernet Emulation) ver 1.3
[    4.844853] Bluetooth: BNEP filters: protocol multicast
[    4.844857] Bluetooth: BNEP socket layer initialized
[    5.708253] Bluetooth: hci0: BCM20702A1 (001.002.014) build 1757
[    5.725206] Bluetooth: hci0: Broadcom Bluetooth Device
[ 1234.665517] Bluetooth: hci0: BCM: chip id 63
[ 1234.682215] Bluetooth: hci0: BCM20702A
[ 1234.683121] Bluetooth: hci0: BCM20702A1 (001.002.014) build 0000
[ 1235.638433] Bluetooth: hci0: BCM20702A1 (001.002.014) build 1757
[ 1235.655265] Bluetooth: hci0: Broadcom Bluetooth Device
[ 1360.811454] Bluetooth: hci0: BCM: chip id 63
[ 1360.827433] Bluetooth: hci0: BCM20702A
[ 1360.828486] Bluetooth: hci0: BCM20702A1 (001.002.014) build 0000
[ 1360.828619] bluetooth hci0: firmware: direct-loading firmware brcm/BCM20702A1-0a5c-21e6.hcd
[ 1361.757724] Bluetooth: hci0: BCM20702A1 (001.002.014) build 1757
[ 1361.774494] Bluetooth: hci0: Broadcom Bluetooth Device

```

### Referencias:
- [Broadcom BCM4352 : Bluetooth does not connect](https://unix.stackexchange.com/questions/359979/broadcom-bcm4352-bluetooth-does-not-connect)
