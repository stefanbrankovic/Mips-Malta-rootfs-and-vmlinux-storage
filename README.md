# Mips Malta rootfs and vmlinux storage

This repository represents storage of **"rootfs"** and **"vmlinux"** files for different **Mips Malta** configurations. Subdirectory names correspond to proper Mips Malta configurations.
Below are terminal commands that start qemu virtual machine for every pair of "rootfs" and "vmlinux" files. The version of **qemu** used in this examples is **5.0.0**.
All roofs images are in compressed format, and must be uncompressed using command "gunzip -k rootfs.ext2.gz" before use. This will keep compressed rootfs images intact, which can be used in case you ever want to revert to using original rootfs-es.

* qemu_mips64r6el_malta:

qemu-system-mips64el -cpu I6400 -M malta -smp 8 -vga std -serial stdio -device virtio-keyboard-pci -kernel <path-to>/vmlinux -drive file=<path-to>/rootfs.ext2,format=raw -append "root=/dev/sda clocksource=GIC console=tty0"

* qemu_mips64r2el_malta:

qemu-system-mips64el -cpu MIPS64R2-generic -M malta -vga std -serial stdio -device virtio-keyboard-pci -kernel <path-to>/vmlinux -drive file=<path-to>/rootfs.ext2,format=raw -append "root=/dev/sda clocksource=GIC console=tty0"

* qemu_mips32r6el_malta:

qemu-system-mipsel -cpu mips32r6-generic -M malta -vga std -serial stdio -device virtio-keyboard-pci -kernel <path-to>/vmlinux -drive file=<path-to>/rootfs.ext2,format=raw -append "root=/dev/sda clocksource=GIC console=tty0"

* qemu_mips32r2el_malta:

qemu-system-mipsel -cpu 24Kf -M malta -vga std -serial stdio -device virtio-keyboard-pci -kernel <path-to>/vmlinux -drive file=<path-to>/rootfs.ext2,format=raw -append "root=/dev/sda clocksource=GIC console=tty0"

* qemu_mips64r6_malta:

qemu-system-mips64 -cpu I6400 -M malta -smp 8 -vga std -serial stdio -device virtio-keyboard-pci -kernel <path-to>/vmlinux -drive file=<path-to>/rootfs.ext2,format=raw -append "root=/dev/sda clocksource=GIC console=tty0"

* qemu_mips64r2_malta:

qemu-system-mips64 -cpu MIPS64R2-generic -M malta -vga std -serial stdio -device virtio-keyboard-pci -kernel <path-to>/vmlinux -drive file=<path-to>/rootfs.ext2,format=raw -append "root=/dev/sda clocksource=GIC console=tty0"

* qemu_mips32r6_malta:

qemu-system-mips -cpu mips32r6-generic -M malta -vga std -serial stdio -device virtio-keyboard-pci -kernel <path-to>/vmlinux -drive file=<path-to>/rootfs.ext2,format=raw -append "root=/dev/sda clocksource=GIC console=tty0"

* qemu_mips32r2_malta:

qemu-system-mips -cpu 24Kf -M malta -vga std -serial stdio -device virtio-keyboard-pci -kernel <path-to>/vmlinux -drive file=<path-to>/rootfs.ext2,format=raw -append "root=/dev/sda clocksource=GIC console=tty0"


