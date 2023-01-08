pkgname=weechat
pkgver=3.8
pkgrel=1
pkgdesc="Fast, light & extensible IRC client (curses UI)"
arch=('x86_64')
url="http://www.weechat.org/"
license=('GPL3')
depends=('gnutls' 'ncurses' 'libgcrypt' 'curl' 'zlib' 'ca-certificates' 'aspell' 'gettext' 'python3' 'perl' 'ruby' 'tcl' 'guile')
makedepends=('cmake' 'pkg-config' 'clang')
options=(!libtool)
source=("http://weechat.org/files/src/${pkgname}-${pkgver}.tar.gz")
sha256sums=('d9d27fac127c724564cf28c6179fa6ecc79a61f9dad09a3b251500f2b0755409')

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
