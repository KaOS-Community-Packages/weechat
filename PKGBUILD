pkgname=weechat
_pkgver=1.1-rc1
pkgver=1.1_rc1
pkgrel=1
pkgdesc="Fast, light & extensible IRC client (curses UI)"
arch=('x86_64')
url="http://www.weechat.org/"
license=('GPL3')
depends=('gnutls' 'ncurses' 'libgcrypt')
makedepends=('cmake' 'pkg-config' 'perl' 'python2' 'lua' 'tcl' 'ruby' 'aspell')
optdepends=('perl' 'python2' 'lua' 'tcl' 'ruby' 'aspell')
options=(!libtool)
source=("https://github.com/weechat/weechat/archive/v${_pkgver}.tar.gz")
#source=("http://weechat.org/files/src/${pkgname}-${pkgver}.tar.gz")
sha1sums=('3cf06cfead34fe351a0e3eb53144cbf3f68bc7e5')

build() {
	cd "${srcdir}/${pkgname}-${_pkgver}"
	cmake -DPREFIX=/usr \
	      -DCMAKE_C_FLAGS="${CMAKE_C_FLAGS} -fPIC -Wall -Wextra -Werror-implicit-function-declaration"
	make
}

package() {
	cd "${srcdir}/${pkgname}-${_pkgver}"
	make DESTDIR="${pkgdir}/" install
}
