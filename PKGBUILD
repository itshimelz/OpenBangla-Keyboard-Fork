# Maintainer: OpenBangla Team <openbanglateam@gmail.com>
pkgname="openbangla-keyboard"
pkgver=3.0.0
pkgrel=1
pkgdesc="An OpenSource, Unicode compliant Bengali Input Method"
arch=('x86_64')
url="https://openbangla.github.io"
license=('GPL3')
depends=('fcitx5' 'qt5-base' 'zstd')
makedepends=('cmake' 'rust' 'ninja')

build() {
    cd "$startdir"
    cmake -B build -S . \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr
    cmake --build build
}

package() {
    cd "$startdir"
    DESTDIR="$pkgdir" cmake --install build
}
