# Based on the following version of extra/libmtp:
# $Id: PKGBUILD 145614 2011-12-24 03:54:58Z dreisner $
#
# Contributor: damir <damir@archlinux.org>
# Contributor: Kevin Edmonds <edmondskevin@hotmail.com>
# Contributor: John Karahalis <john.karahalis@gmail.com>

pkgname=libmtp-git
pkgver=20120114
pkgrel=1
pkgdesc="library implementation of the Media Transfer Protocol"
arch=("i686" "x86_64")
url="http://libmtp.sourceforge.net"
license=('LGPL')
depends=('libusb-compat')
options=('!libtool')
conflicts=('libmtp')
provides=('libmtp')

_gitroot="git://github.com/ynezz/libmtp.git"
_gitname="libmtp"

build() {
  cd "${srcdir}"
  msg "Connecting to Git server...."

  if [ -d $_gitname ]; then
    cd $_gitname && git pull origin
  else
    git clone $_gitroot $_gitname
  fi

  msg "Git checkout done or server timeout"
  msg "Starting make..."

  rm -rf "${srcdir}/${_gitname-build}"
  git clone "${srcdir}/${_gitname}" "${srcdir}/${_gitname-build}"
  cd "${srcdir}/${_gitname-build}"

  ./configure --prefix=/usr
  make
}

package() {
  cd "${srcdir}/${_gitname-build}"
  make DESTDIR="${pkgdir}" install
}
