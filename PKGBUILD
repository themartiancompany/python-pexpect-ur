# Maintainer: Alexander Rødseth <rodseth@gmail.com>
# Contributor: Aaron Schaefer <aaron@elasticdog.com>

pkgname=('python-pexpect' 'python2-pexpect')
pkgver=3.0
pkgrel=1
pkgdesc='Make Python a better tool for controlling and automating other programs'
arch=('any')
url='http://pexpect.readthedocs.org/en/latest/'
license=('MIT')
makedepends=('python' 'python2')
conflicts=('python-pexpect<=2.4')
replaces=('python-pexpect<=2.4')
source=("http://pypi.python.org/packages/source/p/pexpect/pexpect-$pkgver.tar.gz")
sha256sums=('1d6cee0fa5ab212f9ddac9852bab0df5fff11a173ed1bfde9346d5c8aa42d14c')

prepare() {
  cp -r "pexpect-$pkgver" "python2-pexpect-$pkgver"
  sed -i 's:env python:env python2:' "python2-pexpect-$pkgver/pexpect/FSM.py"
}

package_python-pexpect() {
  depends+=('python')
  cd "pexpect-$pkgver"
  python setup.py install --root="$pkgdir"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}


package_python2-pexpect() {
  depends+=('python2')
  cd "python2-pexpect-$pkgver"
  python2 setup.py install --root="$pkgdir"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:
