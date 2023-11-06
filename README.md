
# bsc compressor test workload

see the [original readme](README.orig.md) for information about bsc.

## dependencies

to build this project, the build tools `meson` and `ninja` are required. they can be installed from pretty much every distribution's packages.

## build (native)

```sh
meson setup build
ninja -C build
```

## build (riscv)

```sh
meson setup --cross-file cross/riscv64-linux-gnu.txt build-riscv
ninja -C build-riscv
```
