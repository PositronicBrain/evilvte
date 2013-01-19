# Maintainer: Federico Squartini <federico.squartini@gmail.com>

pkgname=evilvte
pkgver=0.5.2
evtever=0.5.2\~pre1
pkgrel=1
pkgdesc='VTE based, highly customizable terminal emulator'
arch=('i686' 'x86_64')
url='http://www.calno.com/evilvte/'
license=('GPL2')
depends=('vte')
makedepends=('pkg-config')
source=("http://www.calno.com/evilvte/${pkgname}-${evtever}.tar.gz"
        config.h)

md5sums=('b1aa708b6c083f7609e1ea2ba10e43a4'
         '203659938353e76aba78950b4d5ec012')
build(){
    cp $srcdir/config.h $srcdir/${pkgname}-${evtever}/src/
    cd $srcdir/${pkgname}-${evtever}

    ./configure -O2 --prefix=/usr || return 1

    make || return 1

}

package() {
    cd $srcdir/${pkgname}-${evtever}
    make DESTDIR=$startdir/pkg install || return 1
    install -D -m644 gpl-2.0.txt $startdir/pkg/usr/share/licenses/${pkgname}/LICENSE
}
