# Maintainer: Matt C <matt[at]getcryst[dot]al>

pkgname=jade
pkgver=1.1.4
pkgrel=2
pkgdesc="Scriptable backend & TUI Installer for Crystal Linux"
arch=(x86_64)
url="https://github.com/crystal-linux/jade"
license=(GPL3)
depends=(parted)
makedepends=(git cargo)
source=("git+$url#tag=v$pkgver")
sha256sums=('SKIP')

prepare() {
    cd "${srcdir}/${pkgname}"
    cargo fetch --locked --target "$CARCH-unknown-linux-gnu"
}

build() {
    cd "${srcdir}/${pkgname}"
    cargo build --release --frozen
}

package() {
    install -Dm755 "${srcdir}/$pkgname/target/release/jade" -t "${pkgdir}/usr/bin/"
}
