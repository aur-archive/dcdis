# Maintainer: Igor Isaias Banlian <igorisaiasbanlian[at]gmail[dot]com>
# Maintainer: kumyco <kumyco[at]kh[dot]nu>
pkgname=dcdis
pkgver=0.4a
pkgrel=3
pkgdesc="A very simple Dreamcast(tm) disassembler."
url="http://www.ludd.luth.se/~jlo/dc/"
arch=('x86_64' 'i686')
license=('CUSTOM')
depends=('glibc')
source=("http://www.ludd.luth.se/~jlo/dc/$pkgname-$pkgver.tar.gz"
        "dcdis.patch"
        "license.txt")
md5sums=('450752b9a24f60d785f0d04913196554'
         'f0634931243554f6895cf2003c6c7321'
         'ab40e5c8e044c25096b283cea283ad16')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr || return 1
  patch -i "$srcdir/dcdis.patch" || return 1
  make || return 1
  
  install -d -m755 $pkgdir/usr/share/licenses/custom/dcdis
  install -m644 $srcdir/license.txt $pkgdir/usr/share/licenses/custom/dcdis/license.txt || return 1
  install -d -m755 $pkgdir/usr/bin
  install -m755 dcdis $pkgdir/usr/bin/dcdis || return 1
}

# vim:set ts=2 sw=2 et: