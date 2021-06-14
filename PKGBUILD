license=('LGPL2.1')
arch=('x86_64')
pkgname=libcap-ng
pkgver=0.8.2
pkgrel=1
pkgdesc="Library making programming with POSIX capabilities easier than traditional libcap"
depends=('glibc')
url="https://people.redhat.com/sgrubb/libcap-ng/"
source=(https://github.com/stevegrubb/libcap-ng/archive/v${pkgver}/${pkgname}-${pkgver}.tar.gz)
sha512sums=('33832ee16972050a7c5cb20de21d766d5e88f5357db28166b83b05369f7ceea0b1aded39bae2d746d582ad4ee7703c131876fc4bcbc5d4b4eadd7dd429e8cf10')

prepare() {
  cd ${pkgname}-${pkgver}
  autoreconf -fiv
}

build() {
  cd ${pkgname}-${pkgver}
  ./configure \
    --prefix=/usr \
    --enable-static=no \
    --without-python
  make
}

check() {
  cd ${pkgname}-${pkgver}
  make check
}

package() {
  cd ${pkgname}-${pkgver}
  make DESTDIR="${pkgdir}" install
}
