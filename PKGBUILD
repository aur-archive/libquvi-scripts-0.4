# Maintainer: Gustavo Alvarez <sl1pkn07@gmail.com>

pkgname=libquvi-scripts-0.4
pkgver=0.4.21
pkgrel=2
pkgdesc='Embedded lua scripts for libquvi. (0.4.x. branch)'
arch=('any')
url='http://quvi.sourceforge.net/'
license=('LGPL')
depends=('curl' 'lua-socket' 'lua-expat' 'lua-bitop' 'lua-luajson')
options=('!libtool')
source=("http://downloads.sourceforge.net/sourceforge/quvi/libquvi-scripts-${pkgver}.tar.xz"{,.sig})
sha1sums=('86156b5e4b799df95f83afe7f3caa85293a098e6'
          'SKIP')

prepare() {
  rm -fr build
  cp -R "libquvi-scripts-${pkgver}" build
}

build() {
  cd build
  ./configure --prefix=/usr --with-nsfw --with-nlfy --without-manual
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
