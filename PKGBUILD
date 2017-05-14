pkgname=weechat
pkgver=1.8
pkgrel=1
pkgdesc="Fast, light & extensible IRC client (curses UI)"
arch=('x86_64')
url="http://www.weechat.org/"
license=('GPL3')
depends=('gnutls' 'ncurses' 'libgcrypt')
makedepends=('cmake' 'pkg-config' 'perl' 'python2' 'lua' 'tcl' 'ruby' 'aspell')
options=(!libtool)
source=("http://weechat.org/files/src/${pkgname}-${pkgver}.tar.gz")
sha1sums=('6f4c6fc1697851707da6f4147264e86dd43ae948')

build() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	cmake -DPREFIX=/usr 
	make
}

package() {
	cd "${srcdir}/${pkgname}-${pkgver}"
	make DESTDIR="${pkgdir}/" install
}
