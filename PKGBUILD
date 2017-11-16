# Maintainer: Alexander F Rødseth <xyproto@archlinux.org>
# Contributor: Aaron Schaefer <aaron@elasticdog.com>

pkgname=('python-pexpect' 'python2-pexpect')
pkgver=4.3.0
pkgrel=1
pkgdesc='For controlling and automating other programs'
arch=('any')
url='http://pexpect.readthedocs.org/en/stable/'
license=('MIT')
makedepends=('python' 'python2')
source=('https://pypi.python.org/packages/f8/44/5466c30e49762bb92e442bbdf4472d6904608d211258eb3198a11f0309a4/pexpect-4.3.0.tar.gz')
sha256sums=('00ab0872f80f5db740499e7a1283a7c3b97bea542d72df84d83dea17d0afd2d9')

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
