_pkgname=victus-pipewire
pkgname="${_pkgname}"
pkgver=0.0.1
pkgrel=1
pkgdesc="Pipewire audio DSP for internal speakers of the HP Victus laptop"
arch=('any')
url='https://github.com/ther0n/hp-victus-pipewire/tree/main/hp-victus-pipewire'
license=('MIT')
depends=(
  'lv2'
  'bankstown'
  'lsp-plugins-lv2'
  'pipewire'
)
optdepends=()
provides=(
  "${_pkgname}=${pkgver}"
)
replaces=(
  "${_pkgname}<${pkgver}"
)
conflicts=(
  "${_pkgname}"
)
source=(
  'hp-victus-pipewire::git+https://github.com/ther0n/hp-victus-pipewire'
)
sha256sums=(
  'SKIP'
)

package() {
  cd "${srcdir}/hp-victus-pipewire/pipewire.conf.d/"
  install -dDm0755 "${pkgdir}/usr/share/pipewire/pipewire.conf.d/"
  install -v -D -m0644 "victus-mp-l-48k.wav" "${pkgdir}/usr/share/pipewire/pipewire.conf.d/victus-mp-l-48k.wav"
  install -v -D -m0644 "victus-mp-r-48k.wav" "${pkgdir}/usr/share/pipewire/pipewire.conf.d/victus-mp-r-48k.wav"
  install -v -D -m0644 "sink-victus.conf" "${pkgdir}/usr/share/pipewire/pipewire.conf.d/sink-victus.conf"
}
