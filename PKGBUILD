# Maintainer: Yosef Or Boczko <yoseforb@gnome.org>

_pkgname=glib-networking
pkgname=$_pkgname-git
pkgver=2.45.1.1.g9d13dde
_realver=2.45.1
pkgrel=1
pkgdesc="Network-related giomodules for glib"
arch=(i686 x86_64)
url="http://www.gtk.org/"
license=(GPL2)
depends=(glib2 libproxy gnutls ca-certificates gsettings-desktop-schemas)
makedepends=(intltool git)
options=('!libtool')
install=glib-networking.install
replaces=('glib-networking')
provides=('glib-networking')
conflicts=("glib-networking=$_realver")
source=('git://git.gnome.org/glib-networking')
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"
  git describe --always | sed 's|-|.|g'
}

build() {
  cd "$srcdir/$_pkgname"
  ./autogen.sh --prefix=/usr --sysconfdir=/etc \
    --libexecdir=/usr/lib/$pkgname --disable-static --enable-gtk-doc
  make
}

package() {
  cd "$srcdir/$_pkgname"
  make DESTDIR="$pkgdir" install
}
