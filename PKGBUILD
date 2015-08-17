# Maintainer: Limao Luo <luolimao+AUR@gmail.com>
# Maintainer: Jeremy Sands <cto@jeremysands.com>

pkgname=parsedatetime
pkgver=0.8.7
pkgrel=2
pkgdesc="Parse human-readable date/time text"
arch=(any)
url=http://code-bear.com/code/$pkgname
license=(Apache)
depends=(python2)
source=($url/$pkgname-$pkgver.tar.gz)
sha256sums=('9b52f8b25f2f5e29e6b46bb5b37faea77396e5068a1b2828f60149d59bb636f6')
sha512sums=('28d949423ae31dee410f64878563946d0b8180afccd773e889961d3c89ecb303665e572a870a7b7ed785ed2900db0f99702b1276240746a00d9d6687427db79d')

package() {
    cd "$srcdir"/$pkgname-$pkgver/
    find -name '*.py' -type f -exec sed -ri 's:^#!/usr/bin/(env )?python$:&2:' '{}' \;
    export PYTHONPATH="$pkgdir/usr/lib/python2.7/site-packages/"
    install -d "$PYTHONPATH"
    python2 setup.py install --prefix "$pkgdir/usr"
}
