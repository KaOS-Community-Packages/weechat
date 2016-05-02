pkgname=weechat
pkgver=1.5
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
sha1sums=('d7b0341caab91b06ea6a99df9c32665ca04641ad')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	cmake -DPREFIX=/usr 
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make DESTDIR="${pkgdir}/" install
}
