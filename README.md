# Build full Linux system for Aarch64

Build a complete bootable Linux image (bootloader, rootfs, kernel, etc.) for Aarch64. The rootfs is made minimum with busybox.

```bash
./build_image.sh
```

To emulate bootloader:

```bash
qemu-system-aarch64 -machine virt -cpu cortex-a57 -bios u-boot.bin
```

To emulate kernel and rootfs:

```bash
qemu-system-aarch64 -kernel linux/arch/arm64/boot/Image -initrd rootfs.cpio.gz -machine virt -cpu cortex-a53 -m 1G -nographic -append "root=/dev/mem"
```

TODO: combine anything to final firmware image and emulating on that.
