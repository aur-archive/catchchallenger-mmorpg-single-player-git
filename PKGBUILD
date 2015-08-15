# Maintainer: Nyutag <tanguy at metatux dot fr>
pkgname=catchchallenger-mmorpg-single-player-git
pkgver=latest
pkgrel=2
pkgdesc="openSource oldschool MMORPG"
arch=('i686' 'x86_64')
url="http://catchchallenger.first-world.info/"
license=('GPL')
depends=('qt5-multimedia' 'qt5-script')
optdepends=('catchchallenger-datapack-git: free datapack')
makedepends=('git')
_gitroot="git://github.com/alphaonex86/CatchChallenger.git"
source=('catchchallenger-single-player' "${pkgname}"::"${_gitroot}")
md5sums=('f99426ef3423c44f43aa67b7bea730f5'
         'SKIP')
 
build() {
  cd "${srcdir}/${pkgname}/client/single-player/"
  qmake *.pro
  make
}
 
package() {
  install -D -m755 "${srcdir}/${pkgname}/client/single-player/catchchallenger-single-player" "$pkgdir/usr/share/catchchallenger-mmorpg-single-player/catchchallenger-single-player"
  install -D -m755 "${srcdir}/catchchallenger-single-player" "$pkgdir/usr/bin/catchchallenger-single-player"
  echo "***Download the database folder in /usr/share/${pkgname}/***"
  echo "***If catchchallenger-datapack is broken, you can find a nonfree one at http://pkmn-i2p.first-world.info/datapack-pkmn.tar.xz***"
}
