# Maintainer: Kochetkov Andrey <gornet@gmail.com>

pkgname=gtkevemon-hg
pkgver=161.b026684e8196
pkgrel=2
pkgdesc="GTK clone of EveMon skill monitor for EVE Online"
arch=('i686' 'x86_64')
url="https://bitbucket.org/BattleClinic/gtkevemon"
license=('GPL3')
depends=('gtk2' 'gtkmm' 'libxml2' 'openssl')
makedepends=('mercurial')
provides=('gtkevemon' 'gtkevemon-svn')
conflicts=('gtkevemon' 'gtkevemon-svn')
options=()
install=
source=('hg+https://bitbucket.org/BattleClinic/gtkevemon')
md5sums=('SKIP')

pkgver() {
    cd gtkevemon
    echo "$(hg identify -n).$(hg identify -i)"
}

build() {
    cd "${srcdir}/gtkevemon/gtkevemon"
    make
}

package() {
    cd "${srcdir}/gtkevemon/gtkevemon"
    make INSTALL_BIN=$pkgdir/usr/bin \
        INSTALL_DIR_ICON=$pkgdir/usr/share/pixmaps \
        INSTALL_DIR_DESK=$pkgdir/usr/share/applications \
        install
}
