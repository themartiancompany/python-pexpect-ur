# Maintainer: Alexander F Rødseth <xyproto@archlinux.org>
# Contributor: Aaron Schaefer <aaron@elasticdog.com>

pkgname=('python-pexpect' 'python2-pexpect')
pkgver=4.6.0
pkgrel=2
pkgdesc='For controlling and automating applications'
arch=('any')
url='https://pexpect.readthedocs.org/en/stable/'
license=('MIT')
makedepends=('git' 'python' 'python2')
source=("git+https://github.com/pexpect/pexpect#tag=${pkgver%%.0}")
sha512sums=('SKIP')

prepare() {
  cp -r pexpect python2-pexpect
  sed -i 's,env python,env python2,' python2-pexpect/pexpect/FSM.py
}

package_python-pexpect() {
  depends+=('python' 'python-ptyprocess')

  cd pexpect
  python setup.py install --root="$pkgdir"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

package_python2-pexpect() {
  depends+=('python2' 'python2-ptyprocess')

  cd python2-pexpect
  python2 setup.py install --root="$pkgdir"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim: ts=2 sw=2 et:
# getver: pypi.python.org/pypi/pexpect
