# Maintainer: Alexander F Rødseth <xyproto@archlinux.org>
# Contributor: Aaron Schaefer <aaron@elasticdog.com>

pkgname=('python-pexpect' 'python2-pexpect')
pkgver=4.2.0
pkgrel=1
pkgdesc='Make Python a better tool for controlling and automating other programs'
arch=('any')
url='http://pexpect.readthedocs.org/en/stable/'
license=('MIT')
makedepends=('python' 'python2')
conflicts=('python-pexpect<=2.4')
replaces=('python-pexpect<=2.4')
source=("https://pypi.python.org/packages/b3/7b/7b3659b9d7059d6d21e23b2464c5c84bffd4a34450cbf0ed19c9a8a4a52f/pexpect-4.2.0.tar.gz")
md5sums=('8071ec5df0f3d515daedafad672d1632')

prepare() {
  cp -r "pexpect-$pkgver" "python2-pexpect-$pkgver"
  sed -i 's:env python:env python2:' "python2-pexpect-$pkgver/pexpect/FSM.py"
}

package_python-pexpect() {
  depends+=('python' 'python-ptyprocess')
  cd "pexpect-$pkgver"
  python setup.py install --root="$pkgdir"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}


package_python2-pexpect() {
  depends+=('python2' 'python2-ptyprocess')
  cd "python2-pexpect-$pkgver"
  python2 setup.py install --root="$pkgdir"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:
