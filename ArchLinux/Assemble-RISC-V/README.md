[⬅ Back](../)

# Assemble, Link, and Run RISC-V files on x86-64 with QEMU on Arch Linux

Upgrade the system:

```
sudo pacman -Syu
```

Install RISC-V Toolchain and QEMU User Mode:
```
sudo pacman -S riscv64-linux-gnu-binutils qemu-user 
```

Create an Assembly Source File:

```
nano test.s
```

Paste the following code into test.s, then save with Ctrl+S and exit with Ctrl+X::

```
.global _start

_start:
    li a0, 5
    li a7, 93
    ecall

```

Assemble the File:
```
riscv64-linux-gnu-as test.s -o test.o
```

Link the Object file:
```
riscv64-linux-gnu-ld test.o -o test
```

Finally, run the Binary with QEMU:
```
qemu-riscv64 ./test ; echo $?
```

You should see 5 printed to the terminal — this is the exit code set by the li a0, 5 instruction.

![Alt text](run.png)
