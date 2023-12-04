# QEMU AArch64 Virt Bare Bones

Inspiration: https://wiki.osdev.org/QEMU_AArch64_Virt_Bare_Bones

## Compiling the kernel

```
$ aarch64-none-elf-as boot.s -o boot.o
$ aarch64-none-elf-gcc -ffreestanding -c kernel.c -o kernel.o
$ aarch64-none-elf-ld -nostdlib -Tlinker.ld boot.o kernel.o -o kernel.elf
```

## Booting our kernel

```
$ qemu-system-aarch64 -machine virt -cpu cortex-a57 -kernel kernel.elf -nographic
Hello world!
```
