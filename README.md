# patch-for-riscv-gnu-toolchain
patch for riscv-gnu-toolchain

1. get sources:
```
$ git clone https://github.com/UCTECHIP/riscv-gnu-toolchain.git
$ cd riscv-gnu-toolchain
$ git checkout uctechip
$ git submodule update --init --recursive
$ cd riscv-gcc
$ git checkout uctechip
$ cd riscv-binutils
$ git checkout uctechip
```

2. build:
for newlib:
```
$ ./configure --prefix=/opt/riscv
$ make
```

for linux:
```
$ ./configure --prefix=/opt/riscv
$ make linux
```

