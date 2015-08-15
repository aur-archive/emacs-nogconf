# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname=emacs-nogconf
pkgver=24.2
pkgrel=1
pkgdesc="Emacs without gconf"
arch=('i686' 'x86_64')
url="http://ftp.gnu.org/pub/gnu/emacs/"
license=('GPL3')
groups=()
depends=('libpng' 'libtiff' 'librsvg' 'giflib' 'gtk2' 'libxpm' 'libjpeg>=7' 'hicolor-icon-theme')
makedepends=('pkgconfig' 'texinfo' 'gpm')
optdepends=()
provides=('emacs=$pkgver')
conflicts=('emacs' 'emacs-nox' 'emacs-otf' 'emacs-cvs' 'emacs-git' 'emacs-bzr')
replaces=()
backup=()
options=()
changelog=
source=("${url}emacs-$pkgver.tar.bz2")
noextract=()
md5sums=('1676803a50e8adc817fdaaebb9234f14')


build() {
  cd "$srcdir/emacs-$pkgver"

  CFLAGS="-g -O2 -fno-optimize-sibling-calls" ./configure --prefix=/usr --without-pop --with-x-toolkit=gtk --without-xaw3d --without-gconf --with-x
  make
}

package() {
  cd "$srcdir/emacs-$pkgver"

  make DESTDIR="$pkgdir/" install
}
