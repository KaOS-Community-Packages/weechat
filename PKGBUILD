pkgname=weechat
pkgver=2.4
pkgrel=1
pkgdesc="Fast, light & extensible IRC client (curses UI)"
arch=('x86_64')
url="http://www.weechat.org/"
license=('GPL3')
depends=('gnutls' 'ncurses' 'libgcrypt')
makedepends=('cmake' 'pkg-config' 'perl' 'python2' 'lua' 'tcl' 'ruby' 'aspell' 'clang')
options=(!libtool)
source=("http://weechat.org/files/src/${pkgname}-${pkgver}.tar.gz")
sha1sums=('2b295ceab5260c9a52da89a6e4d0c5bfa6351663')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	export CC=/usr/bin/clang
	cmake -DPREFIX=/usr \
	      -DCMAKE_C_COMPILER_ID=Clang
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make DESTDIR="${pkgdir}/" install
}
