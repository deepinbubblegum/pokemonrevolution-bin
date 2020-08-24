pkgname=pokemonrevolution-bin
pkgver=22.8.2020
pkgrel=1
pkgdesc="A free-to-play, fan-made, MMO game that is predicated around the official Pokémon games."
arch=('x86_64')
url="https://pokemon-revolution-online.net"
depends=('gcc-libs' 'desktop-file-utils')
makedepends=('p7zip')
optdepends=('gtk2: required for the Unity ScreenSelector plugin')
conflicts=('pokemon-revolution-online')
source=(https://ddl.pokemonrevolution.net/PROClient_linux.7z)
#https://ddl.pokemonrevolution.net/PROClient_linux.7z
sha256sums=('9b127ad358bf3f0fbe72271cb31b465a01d422a09f5715adaa7755e2adfd85a3')
package() {
  # CREATE FOLDERS
  install -d -m755 "${pkgdir}/opt/Pokemon Revolution"
  install -d -m755 "${pkgdir}/usr/share/pixmaps"
  install -d -m755 "${pkgdir}/usr/share/applications"
  install -d -m755 "${pkgdir}/usr/bin/"

  #ICON FILE
  install -D -m644 "${srcdir}/PROClient/PROClient_Data/Resources/UnityPlayer.png" "${pkgdir}/usr/share/pixmaps/pokemonrevolution.png"

  #Desktop FILE
  install -D -m644 "${srcdir}/pokemon-revolution.desktop" "${pkgdir}/usr/share/applications/pokemon-revolution.desktop"
 
  #SCRIPT FILE
  install -D -m755 "${srcdir}/pokemonrevolution" "${pkgdir}/usr/bin/pokemonrevolution"

  # MOVE CONTENT
  cp -R "${srcdir}/PROClient/" "${pkgdir}/opt/Pokemon Revolution/"
  install -D -m755 "${srcdir}/PROClient/PROClient.x86_64" "${pkgdir}/opt/Pokemon Revolution/PROClient/PROClient.x86_64"
  chmod 755 "${pkgdir}/opt/Pokemon Revolution"
}