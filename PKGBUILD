# Maintainer: BanHammer  <no@e.mail>

pkgname=wireguird
pkgver=1.0.0
pkgrel=2

pkgdesc="Gtk gui client for Wireguard"
arch=("x86_64")
license=("custom:wireguird")
categories=("network")

options=(!strip)
url=https://github.com/UnnoTed/wireguird

depends=("wireguard-tools" "gtk3" "libappindicator-gtk3" "resolvconf")
optdepends=()

provides=(wireguird)
conflicts=(wireguird)

source=("${pkgname}-${pkgver}.deb::https://github.com/UnnoTed/wireguird/releases/download/v1.0.0/wireguird_amd64.deb")
md5sums=("SKIP")

prepare() {
    tar -xf data.tar.zst
    echo "Categories=Network" >> "./usr/share/applications/${pkgname}.desktop"
    echo "GenericName=Gtk gui client for Wireguard" >> "./usr/share/applications/${pkgname}.desktop"
}

package() {
    cp -dr --no-preserve=ownership opt usr "${pkgdir}"/
    install -D -m0644 "${pkgdir}"/opt/${pkgname}/Icon/128x128/wireguard.png "${pkgdir}"/usr/share/pixmaps/${pkgname}.png
    chmod 4755 "${pkgdir}"/opt/${pkgname}/wireguird
}
