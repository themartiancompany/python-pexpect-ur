# Maintainer: Alexander F Rødseth <xyproto@archlinux.org>
# Contributor: Aaron Schaefer <aaron@elasticdog.com>

pkgname=('python-pexpect' 'python2-pexpect')
pkgver=4.1.0
pkgrel=1
pkgdesc='Make Python a better tool for controlling and automating other programs'
arch=('any')
url='http://pexpect.readthedocs.org/en/stable/'
license=('MIT')
makedepends=('python' 'python2')
conflicts=('python-pexpect<=2.4')
replaces=('python-pexpect<=2.4')
source=("https://pypi.python.org/packages/56/2b/9c9c113fb88082950067a42cc99e3c61f1df72035f89bb0bdf0a60308ca0/pexpect-$pkgver.tar.gz")
md5sums=('562a1a21f2a60b36dfd5d906dbf0943e')

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
