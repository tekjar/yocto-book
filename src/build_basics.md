##BUILD SETUP & BUILD

####UBUNTU 15.10 SETUP

```
sudo apt-get install gawk wget git-core diffstat unzip texinfo gcc-multilib build-essential chrpath socat libsdl1.2-dev xterm make xsltproc docbook-utils fop dblatex xmlto autoconf automake libtool libglib2.0-dev python-gtk2 bsdmainutils screen
```

poky incorporates stable bitbake release. So to get started with yocto, we just need to get poky

```
sudo install -o $(id -u) -g $(id -g) -d /opt/yocto 
$ cd /opt/yocto 
$ git clone --branch dizzy git://git.yoctoproject.org/poky
```


The **Poky build system** supports virtualized QEMU machines for the following architectures: 

* ARM (qemuarm) 
* x86 (qemux86) 
* x86-64 (qemux86-64) 
* PowerPC (qemuppc) 
* MIPS (qemumips, qemumips64)


Poky also supports some reference hardware Board Support Packages (BSPs), representative of the architectures just listed. These are those BSPs

* Texas Instruments Beaglebone (beaglebone) 
* Freescale MPC8315E-RDB (mpc8315e-rdb) 
* Intel x86 based PCs and devices (genericx86 and genericx86-64) 
* Ubiquiti Networks EdgeRouter Lite (edgerouter)



####ORGANIZING BUILD DIR & STARTING BUILD

There is no right way to structure the build directories when you have multiple projects, but a good practice is to have **one build directory per architecture or machine type**. 

They can all share a common downloads folders, and even a shared state cache (this will be covered later on), so keeping them separate won't affect the build performance, but it will allow you to develop on multiple hardware projects simultaneously
