# Maintainer: Alexander F Rødseth <xyproto@archlinux.org>
# Contributor: Aaron Schaefer <aaron@elasticdog.com>

pkgname=('python-pexpect' 'python2-pexpect')
pkgver=4.4.0
pkgrel=1
pkgdesc='For controlling and automating applications'
arch=('any')
url='https://pexpect.readthedocs.org/en/stable/'
license=('MIT')
makedepends=('python' 'python2')
source=("https://pypi.python.org/packages/fa/c3/60c0cbf96f242d0b47a82e9ca634dcd6dcb043832cf05e17540812e1c707/pexpect-$pkgver.tar.gz")
sha256sums=('67b85a1565968e3d5b5e7c9283caddc90c3947a2625bed1905be27bd5a03e47d')

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

# vim: ts=2 sw=2 et:
# getver: pypi.python.org/pypi/pexpect
