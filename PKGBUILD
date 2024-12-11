# Maintainer: N1kO23 <niko.huuskonen.00@gmail.com>
# Forked from harttle <yangjvn@126.com>, huge thanks to your contribution
pkgname=macbook-lighter
pkgver=v0.0.2.5.021348d
pkgrel=1
pkgdesc="Macbook screen/keyboard backlight CLI and auto-adjust on ambient light"
arch=(any)
url="https://github.com/N1kO23/macbook-lighter"
license=('GPL')
depends=('bc')
makedepends=('git')
provides=()
conflicts=()
source=('git+https://github.com/N1kO23/macbook-lighter.git')
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$pkgname"
  git describe --tags | sed 's|-|.|g'
}

package() {
  cd "$srcdir/$pkgname"
  [ ! -f $pkgdir/etc/macbook-lighter.conf ] && install -Dm644 macbook-lighter.conf $pkgdir/etc/macbook-lighter.conf
  install -Dm644 "macbook-lighter.service" "$pkgdir/usr/lib/systemd/system/macbook-lighter.service"
  install -Dm755 "src/macbook-lighter-ambient.sh" "$pkgdir/usr/bin/macbook-lighter-ambient"
  install -Dm755 "src/macbook-lighter-screen.sh" "$pkgdir/usr/bin/macbook-lighter-screen"
  install -Dm755 "src/macbook-lighter-kbd.sh" "$pkgdir/usr/bin/macbook-lighter-kbd"
}
