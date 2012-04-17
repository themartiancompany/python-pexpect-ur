# Maintainer:
# Contributor: Aaron Schaefer <aaron@elasticdog.com>

pkgname=python-pexpect
pkgver=2.4
pkgrel=1
pkgdesc='A pure Python Expect-like module'
arch=('any')
url='http://pexpect.sourceforge.net/'
license=('MIT')
depends=('python2')
source=("http://pypi.python.org/packages/source/p/pexpect/pexpect-$pkgver.tar.gz")
md5sums=('fe82d69be19ec96d3a6650af947d5665')

package() {
  cd "$srcdir/pexpect-$pkgver"

  # python2 fix
  sed -i 's_#!/usr/bin/env python_#!/usr/bin/env python2_' FSM.py

  python2 setup.py install --root="$pkgdir"
  install -D -m644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
