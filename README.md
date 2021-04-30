# manjaro-linux512-kernel-custom
Custom PKGBUILD for building linux kernel with custom changes with Arch Build System and Manjaro patches
This repository is for the 5.12 Linux Kernel, and uses includes the default config and patches from the [official Manjaro repository](https://gitlab.manjaro.org/packages/core/linux512/-/tree/master)

## Usage
Clone Linux kernel into /staging and make changes, then use

```set MAKEFLAGS=-j$(nproc) && makepkg -s -f```

to build the pacman compatible packages. Both the kernel and headers package should be installed simulaneously using

```pacman -U {KERNEL-HEADERS}.pkg.tar.zst {KERNEL}.pkg.tar.zst ```

## Troubleshooting
If for some reason the build fails after apply patchs to the kernel, before retrying ensure you reset the kernel to the unpatched state by running these commands. **Ensure you commit any changes you have made before doing this!**

```git clean -fdx``` 

and

```git reset --hard```

## Reference
https://wiki.archlinux.org/index.php/Kernel/Arch_Build_System
