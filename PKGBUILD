pkgname=weechat
pkgver=3.4
pkgrel=1
pkgdesc="Fast, light & extensible IRC client (curses UI)"
arch=('x86_64')
url="http://www.weechat.org/"
license=('GPL3')
depends=('gnutls' 'ncurses' 'libgcrypt' 'curl' 'zlib' 'ca-certificates' 'aspell' 'gettext' 'python3' 'perl' 'ruby' 'tcl' 'guile')
makedepends=('cmake' 'pkg-config' 'clang')
options=(!libtool)
source=("http://weechat.org/files/src/${pkgname}-${pkgver}.tar.gz")
sha256sums=('4b6cacf82d02eb1b327cc293bac8136f5d4220fe0de00383fac5558c0fde6197')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	export CC=/usr/bin/clang
	cmake -DPREFIX=/usr \
	      -DCMAKE_C_COMPILER_ID=Clang \
	      -DENABLE_JAVASCRIPT=OFF \
	      -DENABLE_PHP=OFF \
	      -DENABLE_MAN=OFF \
	      -DENABLE_DOC=OFF
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make DESTDIR="${pkgdir}/" install
}
