pkgname=seeker
pkgver=0.9.2
pkgrel=1
pkgdesc="A productivity with a lot of keyboard shortcut"
arch=('x86_64')
url="https://github.com/fY-Hr/seeker"
license=('MIT')
depends=(
  'gtk3'
  'webkit2gtk-4.1'
  'libappindicator-gtk3'
  'librsvg'
)
makedepends=(
  'npm'
  'bun'
  'rust'
  'cargo'
)
source=(
  "$pkgname-$pkgver.tar.gz::https://github.com/fY-Hr/seeker/archive/refs/tags/v$pkgver.tar.gz"
  "$pkgname.desktop"
)
sha256sums=(
  'SKIP'
  '0a34cb153807284e522336a2f2fb5cac272d20722d8018736914c3628a8fbaac'
)

build() {
  cd "$srcdir/$pkgname-$pkgver"

  export CARGO_TARGET_DIR="$srcdir/target"
  bun install
  bun run tauri build --no-target
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  install -Dm755 "$srcdir/target/release/seeker" "$pkgdir/usr/bin/seeker"
  install -Dm644 "$srcdir/$pkgname.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
  install -Dm644 "src-tauri/icons/128x128.png" "$pkgdir/usr/share/icons/hicolor/128x128/apps/$pkgname.png"
  install -Dm644 "README.md" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
