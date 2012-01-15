# $Id: PKGBUILD 145614 2011-12-24 03:54:58Z dreisner $
# Contributor: damir <damir@archlinux.org>
# Contributor: Kevin Edmonds <edmondskevin@hotmail.com>
# Contributor: John Karahalis <john.karahalis@gmail.com>

pkgname=libmtp
pkgver=1.1.1
pkgrel=1
pkgdesc="library implementation of the Media Transfer Protocol"
arch=("i686" "x86_64")
url="http://libmtp.sourceforge.net"
license=('LGPL')
depends=('libusb-compat')
options=('!libtool')
source=("http://downloads.sourceforge.net/${pkgname}/${pkgname}-${pkgver}.tar.gz")
md5sums=('073e1c2a00ba377f68dce47727e185ae')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
