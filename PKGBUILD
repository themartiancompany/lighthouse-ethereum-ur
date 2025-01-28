# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>

_pkg=lighthouse
pkgname="${_pkg}-ethereum"
pkgver=6.0.1
_commit="0d90135047519f4c2ee586d50e560f7bb2ff9b10"
pkgrel=2
pkgdesc='Ethereum 2.0 client'
arch=(
  'x86_64'
  'aarch64'
  'armv7l'
  'arm'
  'mips'
  'i686'
)
url="https://${_pkg}.sigmaprime.io"
license=(
  'Apache License 2.0'
)
depends=(
  'openssl'
)
makedepends=(
  'cargo'
  'cmake'
  'clang'
  'git'
  'protobuf'
)
_http="https://github.com"
_ns="sigp"
_url="${_http}/${_ns}/${_pkg}"
_tag_name="commit"
_tag="${_commit}"
source=(
  "git+${_url}.git#${_tag_name}=${_commi}"
)
sha256sums=(
  'SKIP'
)

build() {
  cd \
    "${_pkg}"
  env \
    CARGO_INCREMENTAL=0 \
  cargo \
    build \
      --release
}

package() {
  cd \
    "${_pkg}"
  install \
    -Dm755 \
    "${srcdir}/${_pkg}/target/release/${_pkg}" \
    "${pkgdir}/usr/bin/${pkgname}"
  install \
    -Dm644 \
    "${srcdir}/${_pkg}/LICENSE" \
    "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
