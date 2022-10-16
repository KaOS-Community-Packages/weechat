pkgname=weechat
pkgver=3.7
pkgrel=1
pkgdesc="Fast, light & extensible IRC client (curses UI)"
arch=('x86_64')
url="http://www.weechat.org/"
license=('GPL3')
depends=('gnutls' 'ncurses' 'libgcrypt' 'curl' 'zlib' 'ca-certificates' 'aspell' 'gettext' 'python3' 'perl' 'ruby' 'tcl' 'guile')
makedepends=('cmake' 'pkg-config' 'clang')
options=(!libtool)
source=("http://weechat.org/files/src/${pkgname}-${pkgver}.tar.gz")
sha256sums=('b81a7ef89544a7b67dd9f4f4983e46b7af7d42f9371413959310a7bf0bc7ca70')

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
