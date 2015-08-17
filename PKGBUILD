# vim:set ts=2 sw=2 et:
# Contributor: sickhate <sickhate@tux-linux.net>
# Maintainer: alsvartr <nazarov.pn@gmail.com>

pkgname=wallpapoz
pkgver=0.6.2
pkgrel=1
pkgdesc='Enables you to configure Gnome and XFCE desktop wallpapers in unique way'
url="http://vajrasky.wordpress.com/wallpapoz/"
license=('GPL2')
depends=('xorg-xwininfo' 'python2' 'python2-imaging' 'pygtk' 'xorg-xprop')
optdepends=('gnome-python: Native language help documentation support')
arch=('any')
source=("https://github.com/downloads/vajrasky/${pkgname}/${pkgname}-${pkgver}.tar.bz2")
sha256sums=('6b563a4972b2888f75f500040e53228e662659d71cf8d2f67b7a59bc10811899')

package() {
  mkdir ${pkgdir}/usr/

  cd "${srcdir}/${pkgname}-${pkgver}"
  sed -i 's/python/python2/' src/*
  sed -i 's/import Image/from PIL import Image/' setup.py

  python2 setup.py install --installdir="${pkgdir}/usr/"
}
