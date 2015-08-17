# Contributor: kozec <kozec at kozec dot com>
pkgname=pidgin-screenshot
pkgver=0.8.3
_ver=0.8-3
pkgrel=2
pkgdesc="Take a screenshot and send it to a buddy."
arch=('i686' 'x86_64')
url="http://code.google.com/p/pidgin-sendscreenshot/"
license=('GPL')
depends=(pidgin)
makedepends=(intltool)
options=()
source=("http://pidgin-sendscreenshot.googlecode.com/files/pidgin-sendscreenshot-${_ver}.tar.bz2"
	"curl-7.21.7.patch")

build() {
  cd "${srcdir}/pidgin-sendscreenshot-${_ver}"

  patch -Np0 -i "${srcdir}"/curl-7.21.7.patch
  ./configure --prefix=/usr
  make || return 1
}

package () {
  cd "${srcdir}/pidgin-sendscreenshot-${_ver}"
  make DESTDIR="${pkgdir}/" install
}
md5sums=('5f571d78732d109a485b65bb6a767117'
         '420b84ec1c2b139e249db2522953beb7')
