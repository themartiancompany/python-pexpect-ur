# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: Alexander F. Rødseth <xyproto@archlinux.org>
# Contributor: Aaron Schaefer <aaron@elasticdog.com>

pkgname=python-pexpect
pkgver=4.9.0
pkgrel=2
pkgdesc='For controlling and automating applications'
arch=(any)
url='https://pexpect.readthedocs.org/en/stable/'
license=(MIT)
depends=(
  python-ptyprocess
)
makedepends=(
  git
  python-setuptools
)
_commit="aa989594e1e413f45c18b26ded1783f7d5990fe5"
source=(
  # 4.9.0
  "git+https://github.com/pexpect/pexpect#commit=${_commit}"
)
sha512sums=(
  'SKIP'
)
package() {
  cd pexpect
  python \
    setup.py \
      install \
      --root="${pkgdir}"
  install \
    -Dm644 \
    LICENSE \
    "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

