Encrypted Root Partition
====================

Create LUKS Volume
------

Create LVM
------

Configure Bootloader 
-------------

* cryptdevice=/dev/disk/by-partlabel/encryptedroot:decrypt:allow-discards
  * Device containing the luks Volume
  * name of the (mapped) decrypted device
* root=/dev/vg0/lvroot
  * What to mount as the actual Root
* resume=/dev/vg0/lvswap rw quiet
  * Hibernate- (Swap-) Device
* cryptkey=/dev/disk/by-partlabel/key:start:length
  * where the key can be found
  * start: Byte-offset
  * length: Byte-count
* cryptwaitfor=/dev/disk/by-partlabel/key
  * needs modified encrypt hook (install with `make install`)
  * Mait for this device before trying to decrypt anything
