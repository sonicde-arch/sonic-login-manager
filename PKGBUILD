# Maintainer: artist for SonicDE

pkgname=sonic-login-manager
pkgver=6.6.5.1
pkgrel=1
arch=(x86_64)
pkgdesc='Sonic Login Manager'
url="https://github.com/Sonic-DE/$pkgname"
license=(GPL-2.0-or-later)
depends=(glibc
         kauth
         kcmutils
         kconfig
         kcoreaddons
         kdbusaddons
         ki18n
         kio
         kirigami
         kpackage
         kservice
         libgcc
         libxau
         pam
         qt6-5compat
         qt6-base
         qt6-declarative
         sonic-frameworks-windowsystem
         sonic-interface-libraries
         sonic-workspace
         sh
         systemd)
makedepends=(extra-cmake-modules
             qt6-tools)
groups=(sonicde)
conflicts=(plasma-login-manager)
provides=(plasma-login-manager)
replaces=(plasma-login-manager)
source=("$pkgname-$pkgver.tar.gz::$url/archive/refs/tags/$pkgver.tar.gz")

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DCMAKE_INSTALL_LIBEXECDIR=lib \
    -DDBUS_CONFIG_FILENAME=plasma_org.freedesktop.DisplayManager.conf
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}

sha256sums=('0176728e17293d2eb1f24f7c0b7ec1c67c2c91ad5237cffe619640580235763f')
