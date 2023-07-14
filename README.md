   11  apt-get -y install ack antlr3 aria2 asciidoc autoconf automake autopoint binutils bison build-essential bzip2 ccache cmake cpio curl device-tree-compiler fastjar flex gawk gettext gcc-multilib g++-multilib git gperf haveged help2man intltool libc6-dev-i386 libelf-dev libglib2.0-dev libgmp3-dev libltdl-dev libmpc-dev libmpfr-dev libncurses5-dev libncursesw5-dev libreadline-dev libssl-dev libtool lrzsz mkisofs msmtp nano ninja-build p7zip p7zip-full patch pkgconf python2.7 python3 python3-pip libpython3-dev qemu-utils rsync scons squashfs-tools subversion swig texinfo uglifyjs upx-ucl unzip vim wget xmlto xxd zlib1g-dev
   12  git clone https://github.com/coolsnowwolf/lede
   13  cd openwrt
   14  ls
   15  cd lede
   16  sed -i '$a src-git smpackage https://github.com/kenzok8/small-package' feeds.conf.default
   17  ./scripts/feeds update -a
   18  ./scripts/diffconfig.sh > diffconfig
   19  ./scripts/feeds install -a
   20  make config
   21  make menuconfig
   22  rm -rf .config
   23  rm -rf .config
   24  make menuconfig
   25  ./scripts/diffconfig.sh > diffconfig
   26  rm -rf diffconfig
   27  ./scripts/diffconfig.sh > diffconfig
   28  cat diffconfig
   29  make menuconfig
   30  rm -rf diffconfig
   31  ./scripts/diffconfig.sh > diffconfig
   32  cat diffconfig
