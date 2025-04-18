# airmon-ng
kali
Linux
Arch Linux
sudo pacman -Sy base-devel libnl openssl ethtool util-linux zlib libpcap sqlite pcre2 hwloc cmocka hostapd wpa_supplicant tcpdump screen iw usbutils pciutils expect
Debian/Ubuntu
sudo apt-get install build-essential autoconf automake libtool pkg-config libnl-3-dev libnl-genl-3-dev libssl-dev ethtool shtool rfkill zlib1g-dev libpcap-dev libsqlite3-dev libpcre2-dev libhwloc-dev libcmocka-dev hostapd wpasupplicant tcpdump screen iw usbutils expect
Fedora
sudo yum install libtool pkgconfig sqlite-devel autoconf automake openssl-devel libpcap-devel pcre2-devel rfkill libnl3-devel gcc gcc-c++ ethtool hwloc-devel libcmocka-devel make file expect hostapd wpa_supplicant iw usbutils tcpdump screen zlib-devel expect
CentOS/RHEL 7
sudo yum install epel-release
sudo ./centos_autotools.sh
# Remove older installation of automake/autoconf
sudo yum remove autoconf automake
sudo yum install sqlite-devel openssl-devel libpcap-devel pcre2-devel rfkill libnl3-devel ethtool hwloc-devel libcmocka-devel make file expect hostapd wpa_supplicant iw usbutils tcpdump screen zlib-devel
Note: autoconf, automake, libtool, and pkgconfig in the repositories are too old. The script centos_autotools.sh automatically installs dependencies to compile then install the tools.

CentOS/RHEL 8
sudo yum config-manager --set-enabled powertools
sudo yum install epel-release
sudo yum install libtool pkgconfig sqlite-devel autoconf automake openssl-devel libpcap-devel pcre2-devel rfkill libnl3-devel gcc gcc-c++ ethtool hwloc-devel libcmocka-devel make file expect hostapd wpa_supplicant iw usbutils tcpdump screen zlib-devel
openSUSE
sudo zypper install autoconf automake libtool pkg-config libnl3-devel libopenssl-1_1-devel zlib-devel libpcap-devel sqlite3-devel pcre2-devel hwloc-devel libcmocka-devel hostapd wpa_supplicant tcpdump screen iw gcc-c++ gcc ethtool pciutils usbutils expect
Mageia
sudo urpmi autoconf automake libtool pkgconfig libnl3-devel libopenssl-devel zlib-devel libpcap-devel sqlite3-devel pcre2-devel hwloc-devel libcmocka-devel hostapd wpa_supplicant tcpdump screen iw gcc-c++ gcc make expect
Alpine
sudo apk add gcc g++ make autoconf automake libtool libnl3-dev openssl-dev ethtool libpcap-dev cmocka-dev hostapd wpa_supplicant tcpdump screen iw pkgconf util-linux sqlite-dev pcre2-dev linux-headers zlib-dev pciutils usbutils expect
Note: Community repository needs to be enabled for iw

Clear Linux
sudo swupd bundle-add c-basic devpkg-openssl devpkg-libgcrypt devpkg-libnl devpkg-hwloc devpkg-libpcap devpkg-pcre2 devpkg-sqlite-autoconf ethtool wget network-basic software-testing sysadmin-basic wpa_supplicant os-testsuite
Note: hostapd must be compiled manually, it is not present in the repository

BSD
FreeBSD
pkg install pkgconf shtool libtool gcc9 automake autoconf pcre2 sqlite3 openssl gmake hwloc cmocka
DragonflyBSD
pkg install pkgconf shtool libtool gcc8 automake autoconf pcre2 sqlite3 libgcrypt gmake cmocka
OpenBSD
pkg_add pkgconf shtool libtool gcc automake autoconf pcre2 sqlite3 openssl gmake cmocka
NetBSD
pkg_add pkgconf libtool gcc7 automake autoconf pcre2 sqlite3 openssl gmake cmocka
macOS
XCode, Xcode command line tools and HomeBrew are required.

brew install autoconf automake libtool openssl shtool pkg-config hwloc pcre2 sqlite3 libpcap cmocka
Windows
Cygwin
Cygwin requires the full path to the setup.exe utility, in order to automate the installation of the necessary packages. In addition, it requires the location of your installation, a path to the cached packages download location, and a mirror URL.

An example of automatically installing all the dependencies is as follows:

c:\cygwin\setup-x86.exe -qnNdO -R C:/cygwin -s http://cygwin.mirror.constant.com -l C:/cygwin/var/cache/setup -P autoconf -P automake -P bison -P gcc-core -P gcc-g++ -P mingw-runtime -P mingw-binutils -P mingw-gcc-core -P mingw-gcc-g++ -P mingw-pthreads -P mingw-w32api -P libtool -P make -P python -P gettext-devel -P gettext -P intltool -P libiconv -P pkg-config -P git -P wget -P curl -P libpcre2-devel -P libssl-devel -P libsqlite3-devel
MSYS2
pacman -Sy autoconf automake-wrapper libtool msys2-w32api-headers msys2-w32api-runtime gcc pkg-config git python openssl-devel openssl libopenssl msys2-runtime-devel gcc binutils make pcre2-devel libsqlite-devel
GNU/Hurd
Debian
apt-get install build-essential autoconf automake libtool pkg-config libssl-dev shtool zlib1g-dev libpcap-dev libsqlite3-dev libpcre2-dev libhwloc-dev libcmocka-dev screen expect libbsd-dev
Docker containers
We have two repositories on DockerHub:

aircrackng/release: Each release
aircrackng/git: every commit in the git repository
Base command for the git version:

sudo docker run --rm -it aircrackng/git

Available platforms/CPU architectures:

linux/386 (base image: debian:unstable-slim)
linux/amd64 (base image: debian:unstable-slim)
linux/arm/v5 (base image: debian:unstable-slim)
linux/arm/v6 (base image: alpine:3)
linux/arm/v7 (base image: debian:unstable-slim)
linux/arm64/v8 (base image: debian:unstable-slim)
linux/mips64le (base image: debian:unstable-slim)
linux/ppc64le (base image: debian:unstable-slim)
linux/riscv64 (base image: debian:unstable-slim)
linux/s390x (base image: debian:unstable-slim)
Compiling
To build aircrack-ng, the Autotools build system is utilized. Autotools replaces the older method of compilation.

NOTE: If utilizing a developer version, eg: one checked out from source control, you will need to run a pre-configure script. The script to use is one of the following: autoreconf -i or env NOCONFIGURE=1 ./autogen.sh.

First, ./configure the project for building with the appropriate options specified for your environment:

./configure <options>
TIP: If the above fails, please see above about developer source control versions.

Next, compile the project (respecting if make or gmake is needed):

Compilation:
