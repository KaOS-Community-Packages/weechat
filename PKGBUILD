pkgname=weechat
pkgver=3.6
pkgrel=1
pkgdesc="Fast, light & extensible IRC client (curses UI)"
arch=('x86_64')
url="http://www.weechat.org/"
license=('GPL3')
depends=('gnutls' 'ncurses' 'libgcrypt' 'curl' 'zlib' 'ca-certificates' 'aspell' 'gettext' 'python3' 'perl' 'ruby' 'tcl' 'guile')
makedepends=('cmake' 'pkg-config' 'clang')
options=(!libtool)
source=("http://weechat.org/files/src/${pkgname}-${pkgver}.tar.gz")
sha256sums=('f095f452aca0a92d86f46db74d712a890bca130fe1f20f7fad6e515b5c3be644')

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
