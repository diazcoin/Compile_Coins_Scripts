# Compile Coins Scripts

## Instructions
Place this script file in the root directory of the coin. 
This ONLY works for coins with the depends folder in the root directory of the coin. 
Also place root directory in this directory below. 

```
/usr/local/bin
```


It MUST also be logged in as ROOT to avoid errors. 

```
sudo su root
```


The big list of Repos, there are more but start with these. Some lines taken from this link 

```
sudo apt-get update
sudo apt-get upgrade
sudo apt install build-essential libtool autotools-dev automake pkg-config bsdmainutils curl git libboost-all-dev libssl-dev libboost-tools-dev libdb++-dev libevent-dev libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler libevent-dev libboost-all-dev libdb++-dev libssl-dev libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev lib32gcc-4.8-dev g++-arm-linux-gnueabihf gcc-aarch64-linux-gnu nsis libgmp3-dev
sudo apt install g++-mingw-w64-x86-64
sudo apt install software-properties-common
sudo apt install g++-mingw-w64-i686 mingw-w64-i686-dev
sudo apt-get update
sudo apt-get upgrade
```

### For MacOS and ARM Builds - Need these
Source list is from: https://github.com/bitcoin/bitcoin/blob/master/depends/README.md 
```
sudo apt-get install curl librsvg2-bin libtiff-tools bsdmainutils cmake imagemagick libcap-dev libz-dev libbz2-dev python-setuptools
sudo apt-get install curl g++-aarch64-linux-gnu g++-4.8-aarch64-linux-gnu gcc-4.8-aarch64-linux-gnu binutils-aarch64-linux-gnu g++-arm-linux-gnueabihf g++-4.8-arm-linux-gnueabihf gcc-4.8-arm-linux-gnueabihf binutils-arm-linux-gnueabihf g++-4.8-multilib gcc-4.8-multilib binutils-gold bsdmainutils g++-aarch64-linux-gnu binutils-aarch64-linux-gnu g++-aarch64-linux-gnu
```


### Linux 64 bit No GUI Files and GUI QT files (Daemon, TX, CLI, and QT)
```
wget https://raw.githubusercontent.com/nashsclay/Compile_Coins_Scripts/master/linux64_nogui.sh
chmod +x linux64_nogui.sh
./linux64_nogui.sh
```


### Windows 64 bit QT Wallet
```
wget https://raw.githubusercontent.com/nashsclay/Compile_Coins_Scripts/master/win64QT_compile.sh
chmod +x win64QT_compile.sh
./win64QT_compile.sh
```


### Windows 32 bit QT Wallet
```
wget https://raw.githubusercontent.com/nashsclay/Compile_Coins_Scripts/master/win32QT_compile.sh
chmod +x win32QT_compile.sh
./win32QT_compile.sh
```


### MacOSX QT Wallet (Only for High Sierra and possibly older, Mojave still is not compatible!)
No strip needed after compile. This method makes the QT, daemon, cli, and tx files. Send to Mac then do chmod +x filename then run the file.

```
wget https://raw.githubusercontent.com/nashsclay/Compile_Coins_Scripts/master/MacOSX_allfiles_QT_compile.sh
chmod +x MacOSX_allfiles_QT_compile.sh
./MacOSX_allfiles_QT_compile.sh
```


### ARM-32 Bit Wallet (Raspberry Pi)
Don't forget the dependcies!
```
wget https://raw.githubusercontent.com/nashsclay/Compile_Coins_Scripts/master/ARM32_compile.sh
chmod +x ARM32_compile.sh
./ARM32_compile.sh
```

### ARM-64 Bit Wallet (Raspberry Pi)
Don't forget the dependcies!
```
wget https://raw.githubusercontent.com/nashsclay/Compile_Coins_Scripts/master/ARM64_compile.sh
chmod +x ARM64_compile.sh
./ARM64_compile.sh
```

# Old Coin Compile

### Old Coin Linux 64-bit QT
Packages to install per: https://github.com/laanwj/bitcoin-qt/blob/master/doc/readme-qt.rst
```
sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install -y libdb4.8-dev libdb4.8++-dev
sudo apt-get install -y qt4-qmake libqt4-dev build-essential libboost-dev libboost-system-dev \
    libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev \
    libssl-dev
```

Then run these commands in the coins base directory:

```
qmake
make
```

QT file can be found in base folder of the coin source.
