# Maintainer: Carson McManus <carson.mcmanus1@gmail.com>
# Contributor: Mads Mogensen <mads256h at gmail dot com>

_pkgname=steamguard-cli
pkgname=${_pkgname}-git
pkgver=0.4.0.r5.g6d546e6
pkgrel=1
pkgdesc="A command line utility to generate Steam 2FA codes and respond to confirmations."
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
url="https://github.com/dyc3/steamguard-cli"
license=('GPL3')
makedepends=('rust' 'cargo')
source=("git+https://github.com/dyc3/steamguard-cli.git")
sha256sums=('SKIP')

pkgver() {
    cd "${srcdir}/${_pkgname}"
    git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g;s/v//g'
}

build() {
    cd "${srcdir}/${_pkgname}"
    cargo build --release
}

package() {
    install -Dm755 "${srcdir}/${_pkgname}/target/release/${_pkgname}" "${pkgdir}/usr/bin/${_pkgname}"
}
