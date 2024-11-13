# SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>
# Maintainer: Alexander F. Rødseth <xyproto@archlinux.org>
# Contributor: Aaron Schaefer <aaron@elasticdog.com>

_py="python"
_pyver="$( \
  "${_py}" \
    -V | \
    awk \
      '{print $2}')"
_pymajver="${_pyver%.*}"
_pyminver="${_pymajver#*.}"
_pynextver="${_pymajver%.*}.$(( \
  ${_pyminver} + 1))"
_pkg=pexpect
pkgname="${_py}-${_pkg}"
pkgver=4.9.0
pkgrel=2
pkgdesc='For controlling and automating applications'
arch=(
  any
)
url="https://${_pkg}.readthedocs.org/en/stable/"
license=(
  MIT
)
depends=(
  "${_py}>=${_pymajver}"
  "${_py}<${_pynextver}"
  "${_py}-ptyprocess"
)
makedepends=(
  'git'
  "${_py}-setuptools"
)
_commit="aa989594e1e413f45c18b26ded1783f7d5990fe5"
_http="https://github.com"
_ns="${_pkg}"
_url="${_http}/${_ns}/${_pkg}"
source=(
  # 4.9.0
  "${_pkg}-${pkgver}::git+${_url}#commit=${_commit}"
)
sha512sums=(
  'SKIP'
)
package() {
  cd \
    "${_pkg}-${pkgver}"
  "${_py}" \
    setup.py \
      install \
      --root="${pkgdir}" \
      --optimize=1
  install \
    -Dm644 \
    LICENSE \
    "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
