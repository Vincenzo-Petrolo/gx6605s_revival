# C-SKY gx6605s dev board revival

## Rationale
I bought this board long time ago and never used it. During the years, all the links related to how to correctly build a linux kernel disappeared.
The only thing left to do was to dig into the forums, translate the poor existing documentation and eventually I was able to build it.

## Who's for
For those who bought it and don't know what to do with it. 

## Environment
1) Use a 64-bit Ubuntu 16.04 image to build everything. I used the 16.04 docker image.

2) Once the docker image is downloaded, start the container and clone this repository.

3) Install the required packages (more could be needed, sorry!):
```
sudo apt-get install  build-essential git lzip ncurses-dev python unzip bc minicom
```
4) Cd inside the repository and now you can make two targets:
    - **csky_gx6605s_br_defconfig**: Interact with a UART (115200 8N1) connection in the serial terminal
    - **csky_gx6605s_br_fbcon_defconfig**: Interact with a HDMI framebuffer console, can run chocolate-DOOM

5) Make the config using the target you've chosen:
```
make <target>
```

6) Start the build.
```
make
```

7) Once it is done, you will find the usb.img.xz that can be flashed into the USB drive.

8) Plug the USB into the board, either connect it to the PC using USB cable or to the monitor using HDMI.

9) Hit the RESET button on the board

10) Enjoy

## Running DOOM

1) Boot the gx6605s board with the DOOM build installed on the USB flash drive

2) Log-in as root

3) Open DOOM

```
chocolate-doom
```
4) Enjoy

![DOOM on gx6605s](./img/chocolate_doom_demo.jpg)
