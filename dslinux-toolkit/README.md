# DSLinux toolchain
This Docker image includes the DSLinux source code and toolchain. This is useful if you for some reason want to build applications for DSLinux in 2022, or if you want to modify the source code. Developing for DSLinux is covered in their official documentation with the title [PortingHowTo](https://www.dslinux.org/wiki/PortingHowto.html). All steps in building the image are also done according to [the official docs](https://www.dslinux.org/wiki/CompilingDSLinux.html). 


Why a docker image? To simplify development. The older toolchain requires a 386 processor (i.e, a 32 bit one, at least a 32 bit OS). Having this inside an image seems to simplify development a bit (especially on modern systems like my M1 Macbook Air). The tooling seems to be a hazzle to work on modern platforms. I may just have been lazy and jumped to the Docker image solution after a few attempts :P 


Also it might help other people who want to compile ancient software :) [debian/eol](https://hub.docker.com/r/debian/eol) is a great base image for cases like these.


Resulting binaries not tested on real hardware. So far done only in preparation for it. 


## Setup to be able to compile software for DSLinux
If you want to compile software for DSLinux, you should first read the links about porting software above. Run the container from your source directory, and share it as a volume: `docker run -it -v $PWD:/work/myprogram themkat/dslinux`.


- `make menuconfig` (you can just exit to save the defaults. DLDI build is sensible for most "modern" DS Flash Carts)
- `make` (build the kernel and basic tooling. Takes a bloody million years. See note below)
- `make xsh` (to start the cross compilation shell)


**Note: To make it compile I had to disable build of Pixil (PDA gui) and tmsnc (text based MSN client). This can be done in menuconfig, Kernel/Library/Defaults Selection, then User/Vendor settings. Then exit the thing. Now you are back to the terminal for a short moment before a new ncurses menu shows up. Miscellenous applications for Pixil, and Network apps for tmsnc. Deselect with space, then exit and build. Don't worry, you can still build apps that don't depend on these. Have to investigate why these fail during linking...**


Might make an image with the build done later. Not too hard if you want to try yourself (check the bulk build script in the DSLinux SVN repo). Would be fun to be able to use it in Github Actions to produce to some binaries (yes, fun!!!! :D ). 
