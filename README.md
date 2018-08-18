# myos
## 2018-8-18

### 1' download bochs-2.6.9.tar.gz

bochs-2.6.9$ ./configure --enable-debugger --enable-disasm
should use this: ./configure --enable-debugger --enable-disasm --enable-readline LIBS='-lX11'

bochs-2.6.9$ make
bochs-2.6.9$ sudo make install
bochs-2.6.9$ bximage  #make a 1.44 Mb floppy disk image  a.img

### 2' gcc and nasm
sudo apt-get install build-essential nasm

myos$ nasm boot.asm -o boot.bin
myos$ dd if=boot.bin of=a.img bs=512 count=1 conv=notrunc

### 3' bochsrc and run bochs
edit bochsrc, in ubuntu, path is /usr/local/share/bochs/

myos$ bochs
Please choose one: [6]

<bochs:1> c   -- input 'c',means continue

then we will see "hello, OS world!" on top-left of screen



