# Maintainer: Alexander F Rødseth <xyproto@archlinux.org>
# Contributor: Aaron Schaefer <aaron@elasticdog.com>

pkgname=('python-pexpect' 'python2-pexpect')
pkgver=4.3.1
pkgrel=1
pkgdesc='For controlling and automating applications'
arch=('any')
url='https://pexpect.readthedocs.org/en/stable/'
license=('MIT')
makedepends=('python' 'python2')
source=("https://pypi.python.org/packages/14/05/47c8bca66390c9b18c91f6152db4b74eb850382e8e13aa2f06dfb3036466/pexpect-$pkgver.tar.gz")
sha256sums=('8e287b171dbaf249d0b06b5f2e88cb7e694651d2d0b8c15bccb83170d3c55575')

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
