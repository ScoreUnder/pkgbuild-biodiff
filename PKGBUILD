# Maintainer: Daniel Maslowski <info@orangecms.org>

pkgname=biodiff
pkgver=1.1.0
pkgrel=1
pkgdesc="Hex diff viewer using alignment algorithms from biology"
arch=('x86_64')
url="https://github.com/8051Enthusiast/biodiff"
license=('MIT')
makedepends=(cargo)
source=("$pkgname-$pkgver.tar.gz::https://static.crates.io/crates/$pkgname/$pkgname-$pkgver.crate")
sha512sums=('1f277c9829a02d734a99c5e5568c38ddee600ef480a06d2b0dc6467a1b040759c0f21a1b533715caf52ec293ea9c1b6506ade8d3fe518f9f2fcc3651aba8a891')

build() {
    cd "$srcdir/$pkgname-$pkgver"
    export CARGO_TARGET_DIR=target
    cargo build --locked --release --all-features
}

package() {
    cd "$srcdir/$pkgname-$pkgver"
    install -Dm0755 -t "$pkgdir/usr/bin/" "target/release/$pkgname"
}
