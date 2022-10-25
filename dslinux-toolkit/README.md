# DSLinux toolchain -- WIP, working on making it compile
This Docker image includes the DSLinux source code and toolchain. This is useful if you for some reason want to build applications for DSLinux in 2022, or if you want to modify the source code. Developing for DSLinux is covered in their official documentation with the title [PortingHowTo](https://www.dslinux.org/wiki/PortingHowto.html). All steps in building the image are also done according to [the official docs](https://www.dslinux.org/wiki/CompilingDSLinux.html).


Why a docker image? To simplify development. The older toolchain requires a 386 processor, or a 32 bit one. Having this inside an image seems to simplify development a bit. The tooling seems to be a hazzle to work on modern platforms. I may just have been lazy and jumped to the Docker image solution after a few attempts :P 


Not tested on real hardware. So far done only in preparation for it. 
