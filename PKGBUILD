pkgname=weechat
pkgver=1.0.1
pkgrel=1
pkgdesc="Fast, light & extensible IRC client (curses UI)"
arch=('x86_64')
url="http://www.weechat.org/"
license=('GPL3')
depends=('gnutls' 'ncurses' 'libgcrypt')
makedepends=('cmake' 'pkg-config' 'perl' 'python2' 'lua' 'tcl' 'ruby' 'aspell')
optdepends=('perl' 'python2' 'lua' 'tcl' 'ruby' 'aspell')
options=(!libtool)
source=("http://weechat.org/files/src/${pkgname}-${pkgver}.tar.gz")
sha1sums=('1d33591b6c0adc2c30b36a7b349603cbdbcb40b2')

build() {
  cd ${pkgname}-${pkgver}
  cmake -DPREFIX=/usr \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so
  make
}

package() {
  make -C "${pkgname}-${pkgver}" DESTDIR="${pkgdir}/" install
}
