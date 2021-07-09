# patch
1. get `riscv-gnu-toolchain` sources:
```
$ git clone https://github.com/UCTECHIP/riscv-gnu-toolchain.git
$ cd riscv-gnu-toolchain
$ git checkout uctechip
$ git submodule update --init --recursive
```

2. get `riscv-isa-sim` sources:

```
$ git clone https://github.com/UCTECHIP/riscv-isa-sim.git
$ cd riscv-isa-sim
$ git checkout uctechip
```

3. get patch:

```
$ cd riscv-gnu-toolchain
$ git clone https://github.com/UCTECHIP/patch-for-riscv-gnu-toolchain.git
```

4. apply patch:

```
$ cd riscv-gnu-toolchain/riscv-gcc
$ git apply patch-for-riscv-gcc/*.patch
```

```
$ cd riscv-gnu-toolchain/riscv-binutils
$ git apply patch-for-riscv-binutils-gdb/*.patch
```

5. build for newlib:

```
$ cd riscv-gnu-toolchain
$ mkdir build && cd build
$ ../configure --with-arch=rv64gcv --with-abi=lp64d --prefix=/opt/riscv 
$ make
```

6. build for linux:

```
$ cd riscv-gnu-toolchain
$ mkdir build && cd build
$ ../configure --with-arch=rv64gcv --with-abi=lp64d --prefix=/opt/riscv
$ make linux
```

7. build spike

```
$ cd riscv-isa-sim
$ mkdir build && cd build
$ ../configure --prefix=/opt/riscv --with-isa=rv64gcv --enable-histogram
$ make && make install
```

