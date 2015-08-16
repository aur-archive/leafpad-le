# Maintainer:  TDY <tdy@archlinux.info>
# Contributor: rabyte <rabyte__gmail>

pkgname=leafpad-le
pkgver=0.8.17le
pkgrel=1
pkgdesc="Limited edition series of the Leafpad text editor"
arch=('i686' 'x86_64')
url="http://tarot.freeshell.org/leafpad/"
license=('GPL')
depends=('desktop-file-utils' 'gtk2' 'hicolor-icon-theme')
optdepends=('libgnomeprintui: for printing support')
provides=('leafpad')
conflicts=('leafpad')
install=leafpad.install
source=(http://tarot.freeshell.org/leafpad/leafpad-$pkgver.tar.bz2)
md5sums=('d3b6d02ed88e5e458928fc84fefbbba6')

build() {
  cd "$srcdir/leafpad-$pkgver"
  sed -i '3 s/$/ LE/; 9 s/$/;/; 2 c\Version=1.0' data/leafpad.desktop.in
  ./configure --prefix=/usr --enable-chooser
  make
}

package() {
  cd "$srcdir/leafpad-$pkgver"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
