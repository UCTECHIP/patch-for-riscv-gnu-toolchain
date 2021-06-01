# patch-for-riscv-gnu-toolchain

1. getting riscv-gnu-toolchain sources:
```
$ git clone https://github.com/UCTECHIP/riscv-gnu-toolchain.git
$ cd riscv-gnu-toolchain
$ git checkout uctechip
$ git submodule update --init --recursive
```

2. getting patch sources:
```
$ cd riscv-gnu-toolchain
$ git clone https://github.com/UCTECHIP/patch-for-riscv-gnu-toolchain.git
```

3. apply patch
```
$ cd riscv-gnu-toolchain/riscv-gcc
$ git apply ../patch-for-riscv-gnu-toolchain/patch-for-riscv-gcc/0001-fix-vector.md-typo.patch
```

```
$ cd riscv-gnu-toolchain/riscv-binutils
$ git apply ../patch-for-riscv-gnu-toolchain/patch-for-riscv-binutils-gdb/0001-reset-VType-layout-to-RVV-0.9.patch
```

2. build for newlib:
```
$ cd riscv-gnu-toolchain
$ mkdir build && cd build
$ ../configure --prefix=/opt/riscv
$ make
```

3. build for linux:
```
$ cd riscv-gnu-toolchain
$ mkdir build && cd build
$ ../configure --prefix=/opt/riscv
$ make linux
```

